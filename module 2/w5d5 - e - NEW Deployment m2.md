
# Deployment m2

<!--

Status: ready


Slides (shown in the video):
https://docs.google.com/presentation/d/1tHpGGAFdEy9lKv87Qs7uzs4UfQAXGOCSHyXzHQ4RIDU/edit#slide=id.g138c040071e_0_0

-->





## REQUIREMENTS

- make sure all have Adaptable.io INVITATION CODE.




## Day Planning:

- 9am: Deployment (self-guided video)
  - If you have errors while following the video, try to understand what is happening. If you can not solve it, ask for support.

- 2pm: Q&A in the main room

- standup (after Q&A)

- Submit URLs in the students portal. Deadline: 5pm
  - Note: it's Wed., it's normal if there's bugs (but make sure to submit URLs).



## Project 2 Deployment

⛳ Follow instructions in this video:
https://www.loom.com/share/f905d44b81414eeeb5c6ddf0715ae3c5


📌 Links & other things I mention in the video:

- Library project (in case you don't have your own) https://github.com/ironhack-rmt-resources/library-project-deployment-demo
- MongoDB Atlas --> https://account.mongodb.com/account/login
- Pattern for all ip address: 0.0.0.0/0
- Adaptable --> https://adaptable.io/app/signin
- Cheatsheet branches --> https://gist.github.com/luisjunco/d9d0a7d62e7633568533b7214f6af840




<!-->

IMPORTANT:
- share also instructions for seeds file 
- ask students to submit URLs in the students portal (set DEADLINE)

-->




## Submit URLs in students portal


<!-- Note: at the end of the the video, I mention briefly that they need to submit urls in the students portal  -->



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

<!-- @Luis: share instructions on Discord (no need to demo) -->


To seed data on production, you can do the following:

  1. Modify your seeds file so that it points to the production DB (see screenshot)
    - Note: save the changes on this file but do NOT make a commit.

  2. Execute your seeds file in your computer: `node bin/seeds.js`

  3. Confirm that data was created on production (you can do that on MongoDB Compass, connecting to your production DB)

  4. Undo the changes we made in "step 1" (so that they are not added to the repo)
  - Note: this step is important, otherwise you may be pushing your DB credentials to github.

  
![Seed on production](./images/seed-adaptable.png)







## Notes: MongoDB Atlas

- Worth to mention (I don't mention that explicitely in the video)
  - how we can see production DB
  - how to switch between local & production on Compass

- For up-to-date steps & screenshots: check students portal.

- If doing deployment for PROJECT 3: 
  - we need to create a new project (limit of one free cluster per project)





## Notes: Adaptable


Mentioned in the video:

- if you have an organization, make sure all members are owners of the github organization.
- git repo must be in same directory as package.json (if not, it can be configured on adaptable)

- Choose a Deploy Template: "Express App Template"

- Choose Database Type: "NONE" (deploy will be a bit faster)


Not explained in the video:
- how to how to trigger new deploy manually: "update deployment"





## (Extra) Keep me alive

https://github.com/Sepidehatt/KeepMeAlive-hbs-version

<!--
@Luis (Keep me alive):

- test in detail + integrate in our deployment day planning.

- Model.countDocuments() instead of .find() (less chances of students returning the response from DB)


-->




