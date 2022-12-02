
# Deploy to Heroku

<!--

Status: ready

Improvements: create diagram

@Luis: materials in students portal have been updated (a bit more clear)

@todo: create slides to put everything very clear for students


Notes from Karina:
https://docs.google.com/document/d/1TB0Eh8ikV2KEcuGymv0790Osn43kzlRiwVDLxzmLm3w/edit?usp=sharing


-->



## Step 0
- Ask students to create accounts (one account per student, even if they work in teams):
  - Mongo Atlas (DB Server)
  - Heroku (aka "server")

- If working in teams:
  - One person of each team will do the deployment of m2 projects
  - The other team members can watch demo OR deploy a dummy project (eg. library-project)





## Intro:

- Environments:
  https://www.google.com/search?q=development+vs+production+vs+testing&sxsrf=APq-WBsVDYxuaMD6jOfj9WNEw7S2_Q4pPQ:1644998561459&source=lnms&tbm=isch&sa=X&ved=2ahUKEwjViKWX4YP2AhUOLBoKHQHLCdEQ_AUoAXoECAIQAw&biw=1366&bih=625&dpr=1

- Diagram: 
  - Slides "intro to module 2": https://docs.google.com/presentation/d/1tlIuadz1fxwslZcKwxDw413ZuELFg8rbcO8VuocuRUA/edit?usp=sharing


- We need to deploy:
  - DB
  - Server

- Diagram (dev environment, Github, Heroku, DB Server)


<!--
@Luis

- choose who will deploy "project2" vs "library project"

- if you're deploying a codelong we did (ex. the library project), make sure it's a fork, not a clone (cause you'll need to push code)
-->

## IMPORTANT NOTES TO STUDENTS
## IMPORTANT NOTES TO STUDENTS
## IMPORTANT NOTES TO STUDENTS



Deployment & setup takes a lot of time. We need to be efficient.


Make sure all of us....

- 100% attention
  - even if you're not the person doing deployment for "project2"
- Please follow all steps carefully.
- Don't try to go one step ahead (so that we all have the same config) (otherwise we will all have different configuration & different errors)

Note: if you're deploying a codelong we did (ex. the library project), make sure it's a fork, not a clone (cause you'll need to push code)

<!-- 

@Luis: do not push button...

- ![Do not push button](./images/do-not-push-button.png "Do not push button")

-->


## DB: Create cluster [2. Sign Up & Create a Free Cluster]


- (create account)

- login + follow students portal
  - https://account.mongodb.com/account/login

- Security Quickstart
  - choose "username and password"
  - note: choose all lowercase
  - "Where would you like to connect from?": CLOUD ENVIRONMENT
  - ip address: 0.0.0.0/0


- Note: PROJECT 3
  - "theres a max of 1 free cluster per project" -> Create a new project (and then Create Cluster)





## DB: Test
- test on Compass
  - IMPORTANT: replace `username` and `password` to the Connection String.
  - (Optional) customiza DB name: "...mongodb.net/mydbname?"
      - ex: `mongodb+srv://<username>:<password>@<cluster_name>.jqzujwt.mongodb.net/<dbname(optional)>?retryWrites=true&w=majority`
  - If Compass is already open and connected to localhost, you will need to close it and open (the button to "disconnect" may not work, there's a bug)



## Heroku: create account & verify

Create account:
- https://signup.heroku.com/

Login:
- https://id.heroku.com/login


<!--
@Luis:
- can create an account with lj+cohortName@
- (heroku doesn't have social login)
-->

## Heroku: Install Heroku CLI

- Install Heroku CLI (https://devcenter.heroku.com/articles/heroku-cli)
  - Use npm:

    ```
    npm install -g heroku
    ```


## Heroku: Create new App (and configure git remote)

- Create app (follow students portal)
- Configure git (follow students portal)

Note: app name will be public (choose something nice).



## Heroku: Test commit

- make a dummy commit + push to heroku

    ```
    git push heroku main
    ```

- explain remotes
  - git push origin main
  - git push heroku main

- explain "origin" (convention)
  - it is a shorthand name for the remote repository that a project was originally cloned from.
  - it's just a convention  



## Heroku: Environment variables [Set the Config Vars in Heroku]

- follow students portal
  - Note: Remember to add the username and password to the Connection String for Mongo Atlas
  




## (Extra) Automatic Deploys from Github

https://devcenter.heroku.com/articles/github-integration#automatic-deploys





## Heroku: Update mongoose connection and add node version [Set the “Config Vars” update the project files]

- in our code, make sure all DB connections use Environment Variable for the DB URL.

  - Example: 
    
    ```
    require('dotenv').config(); 

    mongoose.connect(
      process.env.MONGODB_URI, 
      ...
    );
    ```

  - note: might apply for `app.js` and `seed.js`


- Update the package.json and specify the version of node (Heroku needs that info -at least for module 3):

  ```
    node --version
  ```

  ```
    "engines": {
      "node": "12.x"
    }
  ```

- Commit + push to github + push to Heroku



## Submit URLs in students portal

<!-- IMPORTANT -->
- Ask students to submit urls (github + heroku) on students portal
<!-- IMPORTANT -->



## Cheatsheet (Heroku commands + Setup to work in pairs)

- https://gist.github.com/luisjunco/daa2962d30075bbdcf407090b1ce5f26




## Concepts that should be clear

- General setup (make diagram)
- Environment variables
- Debugging & errors
- Git "Remotes" (origin / heroku)
- How to push to heroku + when should I push
- Production DB
  - how we can see production
  - how to switch between local & production on Compass
- (extra) How you can run a seed file





## Common problem: unable to push to heroku because .git not in same directory as package.json

Reason:
- git repo in the parent directory + subdirectory with the app and package.json 


Solution:
1. Install these two buildpacks (go to `Dashboard - Settings - Buildpacks`):
  - heroku/nodejs (official)
  - https://github.com/timanovsky/subdir-heroku-buildpack.git

2. Add environment this variable to Heroku:
  - `PROJECT_PATH` (with the name of the subdirectory)






## Common problem: login does not work on production 
- What: on production (heroku), user can create an account and try to login but sessions don't work (ie. we don't keep the logged in status).

- Fix:



  ```js
  // required for the app when deployed to Heroku (in production)
  app.set('trust proxy', 1);
  
  app.use(
    session({
      //...
    })
  );

  ```