
# Deploy to Heroku

<!--

Status: ready

Improvements: create diagram

@Luis: materials in students portal have been updated (a bit more clear)

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

- Diagram what we have: 
  - client + server + DB

- We need to deploy:
  - DB
  - Server

- Diagram (dev environment, Github, Heroku, DB Server)


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


- Security Quickstart
  - choose "username and password"
  - note: choose all lowercase

- Note: if deploying for module 3...
  - "theres a max of 1 free cluster per project" -> Create a new project (and then Create Cluster)


## DB: Setup cluster [3. Setup MongoDB Atlas Cluster]
- follow students portal

- Note: "wWhere would you like to connect from? "
  - Choose "Cloud Environment"
  - Select "advanced" & add 0.0.0.0/0



## DB: Test
- test on Compass
  - IMPORTANT: 
    - REPLACE `username` and `password` to the Connection String.
    - You can also replace DB name (eg. `myFirstDatabase`)
    - If Compass is already open and connected to localhost, you will need to close it and open (the button to "disconnect" may not work, there's a bug)



## Heroku: create account & verify

- https://signup.heroku.com/


## Heroku: Install Heroku CLI

- Install Heroku CLI (https://devcenter.heroku.com/articles/heroku-cli)
  - Use npm:

    ```
    npm install -g heroku
    ```

## Heroku: Create new App (and configure git remote)

- follow students portal

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



## Heroku commands

- Open the app in the browser (from terminal)
  - `heroku open` 


- Get your app’s most recent logs
  - `heroku logs`
  - `heroku logs -n 200`

- Display logs real-time
  - `heroku logs --tail`

- Open a command line terminal in our Heroku server
  - `heroku run bash`
  - Note: this can be helpful, for example, if we want to run our seed file
    - ex: `node bin/seed.js`

- Deploy on production (push our code to the remote repository on heroku):
  `git push heroku main`





## Concepts that should be clear

- General setup (make diagram)
- Environment variables
- Debugging & errors
- How to push to heroku + when should I push
- Git "Remotes" (origin / heroku)
- Production DB
  - how we can see production
  - how to switch between local & production on Compass
- (extra) How you can run a seed file




## Extra: Setup to work in pairs (so that all members can push to Heroku)

Student 1 = the one that deployed the project on heroku
Student 2 = any other student/s in a team


Steps:
- Student 2: shares email address with which they created the account on heroku
- Student 1: heroku > Access > Add collaborator > Add email address of collaborator/s
- Student 2: 
  - in the command line, go to the root directory of m2-project
  - `heroku login` (browser will open)
  - add remote repository
    `heroku git:remote -a nameOfOurProject` 
  - now you should be able to push to heroku, see logs, etc

  
