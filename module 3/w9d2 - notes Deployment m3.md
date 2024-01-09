

# Module 3 Deployment

<!--

- Time: 4h 

- Make sure we do that 3 DAYS BEFORE final presentation,

- Previos day:
  - it is important that we are all present (otherwise you'll need to do with recording)
  - ask students to prepare passwords for Adaptable.io & Mongo Atlas

- Start in the morning

- Difficult & challenging
  -- IT IS IMPORTANT THAT WE ALL FOLLOW THE SAME STEPS
     -- Why: otherwise we will all have different configuration & different errors
  -- Please to follow carefully all steps
  -- Pay 100% attention
  -- Don't try to go one step ahead.
  -- Copy the names of variables (don't type them)


Slides m3 deployment:
https://docs.google.com/presentation/d/19VRo2Bjae3q8b5wNCMKpEG-DrlDN_4Z3-XdHcP4CHZo/edit?usp=sharing


Slides CORS: 
https://docs.google.com/presentation/d/1ccck25g9VXNxWA-GaXquyczZD2VnfD9Zx9lKKgFD2dk/edit?usp=sharing



Notes from Karina:
https://docs.google.com/document/d/16gK6fgwJNGGNyx3Oa9GV40IxHq3RvahjoiBNZFg4Vek/edit?usp=sharing

-->



## Deploy DB on Mongo Atlas

- https://account.mongodb.com/account/login

- IMPORTANT: we need to create a new project (limit of one free cluster per project)


## Test DB (compass)

- test db connection with compass



## Deploy Express App (Adaptable.io / Fly.io)

- Follow steps on m2 lesson.




## TEST BACKEND

- Test API (Postman)
  - We need to add environment variables



## Deploy React App on Netlify

<!-- @Luis: NETLIFY - do this from a students computer -->
<!-- @Luis: NETLIFY - do this from a students computer -->
<!-- @Luis: NETLIFY - do this from a students computer -->


https://netlify.app/


Fix: CI = false

Customise domain name.

IMPORTANT - Fix in this order:
- react app needs to know where is REST API
- REST API needs to know origin for CORS config





## Submit URLs in students portal



<!-- IMPORTANT -->
<!-- IMPORTANT -->
Ask students to submit urls (github x2 + netlify) on students portal
<!-- IMPORTANT -->
<!-- IMPORTANT -->


![screenshot students portal](../media/images/m3-submit-project-urls.png)




## COMMON PROBLEMS:


- IMPORTANT:
- IMPORTANT:
- IMPORTANT: the environment variable for Heroku should `not` finish in a slash.

    eg.  FRONTEND_APP_URL should point to `https://m3-project-management.netlify.app`

    not: `https://m3-project-management.netlify.app/` (notice the slash at the end)





## Fix minor problems:

- Reloading a page on netlify gives a "Not Found" error (eh. https://m3-project-management.netlify.app/login)
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
  - deploy frontent (push to main)

- Troubleshooting (adaptable & netlify logs)

- Disclamer on cloud hosting consumption (eg. Netlify bandwidth)




## Submit URLs in students portal

<!-- IMPORTANT -->
<!-- IMPORTANT -->
Ask students to submit urls (github x2 + netlify) on students portal
<!-- IMPORTANT -->
<!-- IMPORTANT -->


![screenshot students portal](../media/images/m3-submit-project-urls.png)

