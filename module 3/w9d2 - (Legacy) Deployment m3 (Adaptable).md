
# Module 3 Deployment





## Project 3 Deployment

### 1. Using env variables for the location of our API

- Follow this video: https://www.loom.com/share/52429b07880c44b2801956d42dcd2e06


### 2. Intro + Backend:

- Follow this video: https://www.loom.com/share/45058811db3640a2944046a8ffb8cba4

- How to work: 
  - Instead of deploying two applications, you may find it easier to deploy project 3 together.
  - In any case, make sure both of you follow the video.

- Changes in the UI: 
    - example from the video: https://drive.google.com/file/d/1noGvA2uOzr7xTo-gm91aEA9X_C9yHkkq
    - new interface: https://drive.google.com/file/d/1o1aMSjEhCum94H2OhmkMFf6woAx7tYQq

- To configure username and password in MongoDB Atlas, go to `Security > Quickstart` (menu on the left)


MongoDB Atlas:
- IMPORTANT: we need to create a new project (limit of one free cluster per project)
- test db connection with compass

- Test API (Postman)
  - We need to add environment variables



### 3. Frontend + Summary:

- Follow this video: https://www.loom.com/share/1503025f85344dacad7e914cc759ceba



- IMPORTANT: environment variables in our React apps:
  - CRA (in the video): `REACT_APP_XXX` + `process.env.REACT_APP_XXX`
  - Vite (in our case): `VITE_XXX` + `import.meta.env.VITE_XXX`


- Changes in the UI:
  - example from the video: https://drive.google.com/file/d/1GSaam-vABRarKLaq3lzjS-zF5JwKH8-M
  - new interface (sidebar): https://drive.google.com/file/d/10LsxHM-AQmr87IcNfaHiaDXqsN2qmE7e


- During the video I mention some things (ex. `_redirects` file + cheatsheet for `git branches`). You can find them in the description.



### 4. Submit URLs in students portal


As soon as you finish deployment, submit URLs in the students portal.

Make sure you submit the correct urls. 

Screenshot: https://drive.google.com/file/d/1un8OZoDSpSr33VmqziNPOJT8qGVpAwch/view?usp=sharing

Deadline: today, 5pm



### Need help ?

If you're blocked or have doubts, let us know ;)




---
---
---





## COMMON PROBLEMS:


- IMPORTANT:
- IMPORTANT:
- IMPORTANT: the environment variable for Heroku should `not` finish in a slash.

    eg.  FRONTEND_APP_URL should point to `https://m3-project-management.netlify.app`

    not: `https://m3-project-management.netlify.app/` (notice the slash at the end)





## Fix minor problems:

- Reloading a page on netlify gives a "Not Found" error (eg. https://m3-project-management.netlify.app/login)
  Answer: https://answers.netlify.com/t/support-guide-direct-links-to-my-single-page-app-spa-dont-work/126
  Note: definition of "Publish directory": https://docs.netlify.com/configure-builds/get-started/#definitions

  note: `/public/_redirects` needs to go in /public directory
  `/*  /index.html  200`





## (Extra) Keep me alive

https://github.com/Sepidehatt/KeepMeAlive-hbs-version




## Summary & Process & Troubleshooting


- Summary of our setup
  - dev vs. production
  - production (mongodb Atlas + Adaptable + Netlify)

- Remember: the databases for development & production are different

- How to publish changes:
  - push to github
  - deploy backend (push to main)
  - deploy frontend (push to main)

- Troubleshooting (Adaptable & Netlify logs)

- Disclaimer on cloud hosting consumption (eg. Netlify bandwidth)




## Submit URLs in students portal

<!-- IMPORTANT -->
<!-- IMPORTANT -->
Ask students to submit urls (github x2 + netlify) on students portal
<!-- IMPORTANT -->
<!-- IMPORTANT -->






## As a guided workshop / lecture

In case it is done as a guided workshop/lecture, explain the following:

- m3 deployment is complex & takes time
- IT IS IMPORTANT THAT WE ALL FOLLOW THE SAME STEPS
    -- Why: otherwise we will all have different configuration & different errors
- Please to follow carefully all steps
- Pay 100% attention
- Don't try to go one step ahead.
- Copy the names of variables (don't type them)

Time: ~3h 



## Seed file (seed data on production DB)

<!-- @LT: share instructions on Slack (no need to demo) -->
<!-- @todo: create a gist -->


To seed data on production, you can do the following:

  1. Modify your seeds file so that it points to the production DB (see screenshot)
    - Note: save the changes on this file but do NOT make a commit.

  2. Execute your seeds file in your computer: `node bin/seeds.js`

  3. Confirm that data was created on production (you can do that on MongoDB Compass, connecting to your production DB)

  4. Undo the changes we made in "step 1" (so that they are not added to the repo)
  - Note: this step is important, otherwise you may be pushing your DB credentials to github.

  
![Seed on production](../media/images/seed-adaptable.png)


