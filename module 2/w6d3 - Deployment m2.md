

# Deployment m2


<!-- 

Status: 
- ready (updated after m2-m3 swap)


@todo: 
- Record video "continuous deployment + branches" 
- (see slide 27)

-->


## Instructions

⛳ Deployment project 2:
- https://www.loom.com/share/915ec9d82f10412eb1e6fb4f77815cab?sid=1fc15197-4f5d-4336-8f92-e08640bd7d90


📌 Notes:

- Make sure both of you do deployment together.
- Even if your app seems to work, follow the whole video


📮 Submit project urls:

- As soon as you finish deployment, make sure both of you submit URLs in the students portal.
- Screenshot: https://drive.google.com/file/d/1DbOuV-w94tZqaKNWPlnx873xnf_hrsib/view?usp=sharing
- DEADLINE: today, 5pm





<!-- IMPORTANT -->
- Ask students to submit urls (repo + github pages) on students portal
- Set DEADLINE
<!-- IMPORTANT -->



## Notes

- I've tried to keep it generic, so that it serves for m2 + m3.
  - Video explicitly states that p2 & p3 are in pairs + asks both of them to follow the recording.
  - It also includes the concept of environment variables ("for m2, you probably don't need this concept but in m3 we'll need it")
  - End of the video, asks to submit project URLs (showing students portal m2 & m3) 

- Slides used in the recording: https://docs.google.com/presentation/d/1tHpGGAFdEy9lKv87Qs7uzs4UfQAXGOCSHyXzHQ4RIDU/edit?usp=sharing


- Known errors in the recording:
  - not for now.




## Recording Script


- Intro (environments + architecture)
- Deploy on Netlify
  - Create account + login
  - Create our app from a Github repo (may need to add permissions)
- Errors:
  - Build errors (ex. Navbar not defined)
    - how to debug: see error logs on netlify
  - Runtime errors (ex. Cannot read property 'map' of undefined')
    - how to debug: see console in the browser
- Explain: continuous deployment
- Environment variables
  - How to create & use environment variables (dev/production)
- Configure App name (subdomain)
- Fix: "page not found" (create _redirects)
- Submit URLs in the students portal


## How to fix error on page reload

Fix error when user reloads the page on Netlify:
- Explained in the video at 30:28
- https://www.loom.com/share/915ec9d82f10412eb1e6fb4f77815cab?t=1828&sid=c4fbdae9-5157-4aa0-8f64-db30f6d870ad



