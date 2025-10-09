

# Deployment m2



## Notes

- I've tried to keep it generic, so that it serves for m2 + m3.
  - Video explicitly states that p2 & p3 are in pairs + asks both of them to follow the recording.
  - It also includes the concept of environment variables ("for m2, you probably don't need this concept but in m3 we'll need it")
  - End of the video, asks to submit project URLs (showing students portal m2 & m3) 

- Slides used in the recording: 
  - EN: https://docs.google.com/presentation/d/1tHpGGAFdEy9lKv87Qs7uzs4UfQAXGOCSHyXzHQ4RIDU/edit?usp=sharing
  - ES: https://docs.google.com/presentation/d/1lsSrv9H7SI6Qyt7_K2huBbvwonuXwMmA1uNpl4CHvAc/edit?usp=sharing


- Known errors in the recording:
  - not for now.




## Recording Script


- Intro (environments + architecture)
- Deploy on Netlify
  - Create account + login
  - Create our app from a Github repo (may need to add permissions)
- Errors:
  - Build errors (e.g. Navbar not defined)
    - how to debug: see error logs on netlify
  - Runtime errors (e.g. Cannot read property 'map' of undefined')
    - how to debug: see console in the browser
- Explain: continuous deployment
- Environment variables
  - How to create & use environment variables (dev/production)
- Configure App name (subdomain)
- Fix: "page not found" (create _redirects)
- Submit URLs in the students portal

