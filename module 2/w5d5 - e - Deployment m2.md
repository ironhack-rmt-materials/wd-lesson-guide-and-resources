
# Deployment m2

<!--

Status: ready

@Luis: materials in students portal have been updated (a bit more clear)




Notes from Karina:
https://docs.google.com/document/d/1TB0Eh8ikV2KEcuGymv0790Osn43kzlRiwVDLxzmLm3w/edit?usp=sharing

Gist for MongoDB Atlas:
https://gist.github.com/TA-Remote/80801bf13ce27844e1b5b50f858436c7

Gist for Adaptable:
https://gist.github.com/TA-Remote/fa2324189c28491e4f8e16accbc05bf6


-->









## Step 0


<!-- @Luis: make sure all have Adaptable.io INVITATION CODE -->





<!--


ASK IN ADVANCE:


Create your account here (don't need to do anything else, just make sure you have your account created): https://adaptable.io/app/signin?redirect=/app/dashboard



Choose public name for your app.
- ex: my-restaurant.subdomain.com


Choose, from each group, 2 roles:
- Student A: will deploy your project 2
- Student B: will deploy library-project (make sure you have the project available & running)


Those doing the library project, make sure you have it ready in your computer. If you need to replicate:
- fork + clone
- npm install
- npm run dev

-->




- Ask students to create accounts (one account per student, even if they work in teams):
  - Mongo Atlas (DB Server)
  - Fly.io / Adaptable.io (aka "server")

- If working in teams:
  - One person of each team will do the deployment of m2 projects
  - The other team members can watch demo OR deploy a dummy project (eg. library-project)





## Intro:

Slides:
- https://docs.google.com/presentation/d/1tHpGGAFdEy9lKv87Qs7uzs4UfQAXGOCSHyXzHQ4RIDU/edit?usp=sharing


- We need to deploy:
  - DB
  - Server



<!--
@Luis

- choose who will deploy "project2" vs "library project"

- if you're deploying a codelong we did (ex. the library project), make sure it's a fork, not a clone (cause you'll need to push code)
-->



## IMPORTANT NOTES TO STUDENTS
## IMPORTANT NOTES TO STUDENTS
## IMPORTANT NOTES TO STUDENTS


<!--
@todo:
- add the notes below to the slides
-->

Deployment & setup takes time. We need to be efficient:


- Please keep 100% attention
  - even if you're not the person doing deployment for "project2"

- Please follow all steps carefully.

- Don't try to go one step ahead (so that we all have the same config... and same errors) 

Note: if you're deploying a codelong we did (ex. the library project), make sure it's a fork, not a clone (cause you'll need to push code)


If you need the library project:
- fork + clone
- npm install
- npm run dev





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


- If doing deployment for PROJECT 3: 
  - we need to create a new project (limit of one free cluster per project)





## DB: Test
- test on Compass
  - IMPORTANT: replace `username` and `password` to the Connection String.
  - (Optional) customiza DB name: "...mongodb.net/mydbname?"
      - ex: `mongodb+srv://<username>:<password>@<cluster_name>.jqzujwt.mongodb.net/<dbname(optional)>?retryWrites=true&w=majority`
  - If Compass is already open and connected to localhost, you will need to close it and open (the button to "disconnect" may not work, there's a bug)



## Adaptable.io: create account

https://adaptable.io/app/signin




## Create new App


- IMPORTANT: if you have an organization, make sure all members are owners of the github organization (before we go further).


- Select repo from github.

- Select "main" branch

- Choose a Deploy Template: "Express App Template"

- Choose Database Type: "NONE"
  <!-- UPDATE: don't choose DB on Adaptable (deploy will be a bit faster) -->

- Template Settings: keep defaults

- Choose an app name
  - Note: name will be public (ex. https://my-restaurant.adaptable.io)
  <!-- @Luis:  break (so that they agree on the name) -->


- HTTP Listener on PORT: confirm checkbox + click deploy.

- (app takes a bit to build, about 5min)
  <!-- @Luis:  break / pictionary here ??? -->



## Test commit

- make a dummy commit + push to main branch

- git push origin main





## Environment variables

- Note: Remember to add the username and password to the Connection String for Mongo Atlas
  





## Update mongoose connection 

- in our code, make sure all DB connections use Environment Variable for the DB URL.

  - Example: 
    
    ```js
    require('dotenv').config(); 

    mongoose.connect(
      process.env.MONGODB_URI, 
      ...
    );
    ```

  - note: might apply for `app.js` and `seed.js`



- Commit + push to github 



## Submit URLs in students portal

<!-- IMPORTANT -->
<!-- IMPORTANT -->
<!-- IMPORTANT -->

Ask students to submit urls (github + adaptable) on students portal

- "Project 2 Deliverables/GitHub repo"
  - URL to your project's GitHub repository (ie. project2 repo).

- "Project 2 Deliverables/Deployed project"
  - URL of your deployed project (on Adaptable)
  - Note: you may need to get this URL from your partner.

<!-- IMPORTANT -->
<!-- IMPORTANT -->
<!-- IMPORTANT -->



## Seed file (seed data on production DB)

<!-- @Luis: share instructions on slack (no need to demo) -->


To seed data on production, you can do the following:

  1. Modify your seeds file so that it points to the production DB (see screenshot)
    - Note: save the changes on this file but don't make a commit.

  2. Execute your seeds file in your computer: `node bin/seeds.js`

  3. Confirm that data was created on production (you can do that on MongoDB Compass, connecting to your production DB)

  4. Undo the changes we made in step1 (so that they are not added to the repo)
  - Note: this step is important, otherwise you may be pushing your DB credentials to github.

  
![Seed on production](./images/seed-adaptable.png)





## (Extra) Keep me alive

https://github.com/Sepidehatt/KeepMeAlive-hbs-version

<!--
@Luis (Keep me alive):
- Model.countDocuments() instead of .find() (less chances of students returning the response from DB)
-->



## Concepts that should be clear

- General setup (make diagram)
- Environment variables
- Debugging & errors
- Automatic deploys (how to deploy + when should I push...)
- Production DB
  - how we can see production
  - how to switch between local & production on Compass


## Error: 405 from Adaptable
- Jan 2023: me + 4 students had that error
- when we test with Postman, we get a 405 "Not allowed"
- in the response body, can see "nginx" (it's probably an error from Adaptable, not from our code)
- Quick Fix: create a new app on Adaptable (so far it has worked for 2 out of 2)


## Common problem: .git not in same directory as package.json

Reason:
- git repo in the parent directory + subdirectory with the app and package.json 



