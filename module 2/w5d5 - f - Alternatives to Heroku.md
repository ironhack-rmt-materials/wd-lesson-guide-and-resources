


## Alternatives to Heroku (summary)

- adaptable.io
  - pros: 
    - very easy to use 
    - doesn't ask for credit card
    - can deploy from repos on a github organization
    - full support for websockets
  - cons: 
    - still in Beta, at the moment, it requires to signup for an invitation code.
    - build process takes some time (5min ish)
    - can not add collaborators (ex. to see error logs)
- fly.io
  - pros:
    - reliable
  - cons: 
    - asks for credit card
    - I've had some issues & some TAs also reported issues deploying
- cyclic.sh
  - pros: very easy to use
  - cons:
    - no support for web sockets
    - only supports personal repos (atm, it is not possible to deploy repos from a GH organization, even if they are public)
    - prerformance is not great.
- render.com
  - cons: after 15min inactivity it goes iddle and takes a bit longer for the first request


https://wd-ft5thsep.slack.com/archives/C03VAB6NVHD/p1667291035893679






## Adaptable.io

Signup for beta invitation
  - Twitter invitation: https://mobile.twitter.com/adaptableio/status/1540400042065833993


Process:
  - template: Express
  - database: MongoDB



Websockets:
- FAQs say they fully support websockets
- 1 group implemented and it works but had some issues:
  - "We have the live chat working in production, but just for a few seconds and it disconnects after the very first messages" (works on localhost)

2 students had a problem connecting to github repo (PENDING):
- click "missing a repo? Add more GitHub repositories"
- takes time and, in the end, displays a unicorn
- Reason: I'm not sure if students were not able to see the name of the repo (just in case, ask them to search with Ctrl+F) or it was due to permissions.
- how we solved it: 
  - make sure the student is owner of the organization + admin for the repo
  - we logged out 
  - we revoked access to the app.
  - we logged in again & granted access again.
  - to find the repo, do Control + F to make sure we find it.

  - Note1: probably not an issue with adaptable.io, because we had the exact same problem for these same students when we deployed on Netlify (I guess it could be due to configuration for these 2 groups of students or a recent change on github)

  - Note2: one of the students reported it was due to being members of a github organization with a huge number of members (when they left the org., the issue was solved).

1 student was not able to connect (SOLVED)
- after granting access to GH organization, the repo does not appear on the list
- we've tried refreshing the page, starting again, etc (the repo does not appear)
- reason: student was not "owner" of that organization ???
- solution: set him as "owner" -- worked.
