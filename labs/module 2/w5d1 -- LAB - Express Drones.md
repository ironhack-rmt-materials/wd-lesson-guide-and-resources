# LAB | Express Drones

[REPO](https://github.com/ironhack-labs/lab-express-drones)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/0a29ed4743ee175e1cca36355bbb4ad2)

### Goal of the LAB

- practice basic CRUD

### Guidelines for LAB

npm install
npm run dev <---> nodemon server.js

##### IT 1

Create drone model -> don't forget to export / import 
- export model
- in seeds file:
    - import model
    - create array of data
    - establish connection mongoose.connect()  -> copy from db/index.js
    - send it to db Drone.create()
    - !!! run the seed file -> node seeds/drones.seed.js 

##### IT 4 & 5

use req.params. 

- in drone details view, you have all info about the drone , inclduignn  it's ID
- You want to use this ID for edit & delete. 
    - edit -> href
    - delete -> form - action




