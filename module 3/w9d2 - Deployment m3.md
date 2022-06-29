

# Module 3 Deployment

<!--

- Time: 6-8h +

- Make sure we do that 3 DAYS BEFORE final presentation,

- Previos day:
  - it is important that we are all present (otherwise you'll need to do with recording)
  - ask students to prepare passwords for Heroku & Mongo Atlas

- Start in the morning

- Difficult & challenging
  -- IT IS IMPORTANT THAT WE ALL FOLLOW THE SAME STEPS
     -- Why: otherwise we will all have different configuration & different errors
  -- Please to follow carefully all steps
  -- Pay 200% attention
  -- Don't try to go one step ahead.
  -- Copy the names of variables (don't type them)


@todo: create slides to put everything very clear for students


Slides CORS: 
https://docs.google.com/presentation/d/1ccck25g9VXNxWA-GaXquyczZD2VnfD9Zx9lKKgFD2dk/edit?usp=sharing



Notes from Karina:
https://docs.google.com/document/d/16gK6fgwJNGGNyx3Oa9GV40IxHq3RvahjoiBNZFg4Vek/edit?usp=sharing

-->


# Intro


- Environments (dev, staging, production):
  https://nbarger.files.wordpress.com/2010/01/lifecycle_environments2.gif
  https://i.stack.imgur.com/OBQF7.png


- Automation:

  > If we're doing a task frequently, it can be worth to automate the proces...

  Life example: https://www.youtube.com/watch?v=Vzjn9VvprJw



- DevOps CI/CD Explained in 100 Seconds
https://www.youtube.com/watch?v=scEDHsr3APg





- Diagram & common problems: https://stackoverflow.com/q/66503751/11298742





# Deploy Express App on Heroku

- Follow steps on m2 lesson ("Deploy to Heroku"): from section "Login to the Heroku website and Create New App"


# Deploy DB on Mongo Atlas


- Create new project (limit of one free cluster per project)



# TEST BACKEND

- Test DB (Compass)

- Test API (Postman)
  - We need to add environment variables


# Deploy React App on Netlify



# COMMON PROBLEMS:


- IMPORTANT:
- IMPORTANT:
- IMPORTANT: the environment variable for Heroku should `not` finish in a slash.

    eg.  FRONTEND_APP_URL should point to `https://m3-project-management.netlify.app`

    not: `https://m3-project-management.netlify.app/` (notice the slash at the end)





# Fix minor problems:

- Reloading a page on netlify gives a "Not Found" error (eh. https://m3-project-management.netlify.app/login)
  Answer: https://answers.netlify.com/t/support-guide-direct-links-to-my-single-page-app-spa-dont-work/126
  Note: definition of "Publish directory": https://docs.netlify.com/configure-builds/get-started/#definitions


  note: `_redirects ` needs to go in /public directory
  `/*  /index.html  200`



# Summary & Process & Troubleshooting


- Summary of our setup
  - dev vs. production
  - production (mongodb Atlas + Heroku + Netlify)

- Remember: the databases for development & production are different

- How to publish changes:
  - push to github
  - deploy backend (need to push to heroku)
  - deploy frontent (automated, just by pushing to github)

- Work in teams (in case they're in teams, how they can deploy etc)

- Troubleshooting (heroku & netlify logs)

- Disclamer on cloud hosting consumption (eg. Netlify bandwidth)


