

# Some options to deploy Express apps



## render.com
- pros: 
  - No need for credit card 
  - Can deploy from repos on a github organization
- cons: 
 - After 15min inactivity it goes idle and takes a bit longer for the first request (can bypass with a service like UptimeRobot)


## vercel

- For backend/express apps, can use this configuration: https://gist.github.com/Marshall-Bits/664ef4b4f87607eb96d3e12a840adfec

- Limitations:
  - no support for websockets



## adaptable.io

- update: since Sept. 2023, adaptable.io doesn't offer a free plan 

- pros: 
  - Very easy to use
  - Can deploy from repos on a github organization
  - Full support for websockets
- cons: 
  - Build process takes some time (5-8min)
  - Can not add collaborators (ex. to see error logs)
  - Invoking external apis from backend may be problematic in the free plan (in premium plan you can choose region)


## fly.io

- pros:
  - Reliable ?
- cons: 
  - Asks for credit card
  - I've had some issues & some TAs also reported issues deploying


## cyclic.sh

- pros: very easy to use
- cons:
  - No support for web sockets
  - Only supports personal repos (atm, it is not possible to deploy repos from a GH organization, even if they are public)
  - Performance is not great.




## Other options

- Heroku
- Railway (https://railway.app/)




