
# Module 3 Deployment

<!--

Status: 

Slides (shown in the video): https://docs.google.com/presentation/d/19VRo2Bjae3q8b5wNCMKpEG-DrlDN_4Z3-XdHcP4CHZo/edit?usp=sharing


todo: record new video or update to take into account a few updates
- how we will work: ask both students to follow video together (instead of deploying 2 apps)
- current video mentions multiple times that they already have an account from m2 (not anymore since m2-m3 swap)
- ui changes (mongoDB Compass, Atlas, Adaptable, Netlify)
- video 3: environment variables Vite (towards the beginning)


-->





## Day Planning:

- 9am: Deployment (follow the recordings in #class-activities)
  - If you have errors while following the video, try to understand what is happening (if you can not solve it, ask for support).
  - You can also send a request if you want to clarify any point.

- 12:00: standup

- Submit URLs in the students portal. Deadline: 5pm


- Note: it's Tuesday, it's normal if the your project isn't finished yet (but make sure to submit URLs + make sure you submit the correct URL).



---
---
---


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


