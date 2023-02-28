
# Heroku Deployment

<!--

Notes from Karina:
https://docs.google.com/document/d/1TB0Eh8ikV2KEcuGymv0790Osn43kzlRiwVDLxzmLm3w/edit?usp=sharing


-->




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
    
    ```js
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

  ```js
    "engines": {
      "node": "12.x"
    }
  ```

- Commit + push to github + push to Heroku




## Cheatsheet (Heroku commands + Setup to work in pairs)

- https://gist.github.com/luisjunco/daa2962d30075bbdcf407090b1ce5f26






## Common problem: unable to push to Heroku because .git not in same directory as package.json

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