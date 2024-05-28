
# Express - Introduction


<!-- 

update m2-m3 swap:

- there's a few new concepts
  - Request Logging
  - Middleware
  - Working with JSON


@todo: 
- review planning & update Demo (ie. which app we build)
- add quick exercise



Codealong:
- create "IronRestaurant" (iron-restaurant)
- we will evolve it during the following days
- Sample repo: https://github.com/ironhack-apr2024-theScriptSociety/iron-restaurant


-->





## Part 1: some concepts



- Refresh HTTP Verbs
  - slides (Refresh "How the internet works"): https://docs.google.com/presentation/d/1-EgP1r7duakjZ6DXfReHIu9cYwEheAWEd_vDL7JtYiU/edit?usp=sharing



- What is a Framework and why we use it

  <!-- @todo: create slides -->

  - Framework vs library:
    - https://www.digitaltechmedia.in/wp-content/uploads/2020/11/framework-vs-library-dtm.jpg
    - https://qph.cf2.quoracdn.net/main-qimg-b21ba6c5e7ab388225dfafa0c96075d5-pjlq
    - (skip) https://kobaltsolutions.com/wp-content/uploads/2021/02/YOUR-CODE.png


- Brief intro to Express.js
  - MERN stack
  - MERN logos: https://miro.medium.com/max/1400/1*FVtCyRdJ6KOr4YswTtwMeA.jpeg



## Part 2: codealong (from "Create Express App")

<!-- 

Some notes below (not comprehensive)

Follow students portal.

-->


- Demo: create "IronRestaurant" (iron-restaurant)


- Goal today for "IronRestaurant":
    - home
    - contact
    - one image + css
    - nav menu
    - "endpoint" to get a list of pizzas

    Also:
    - Request Logging (morgan)
    - Middleware
      - JSON Middleware - express.json()



- (skip) ask students: how do we want to call our pizza company



Initial setup:

  ```shell
  mkdir iron-restaurant
  cd iron-restaurant
  npm init --yes
  npm install express
  ```


## Static Files

- For images & css, use an `ABSOLUTE PATH` (we will save time tomorrow)



## Nodemon

Some students have problems installing `nodemon`.
  - Just use `sudo`.
  - Alternative: `npx nodemon my-file.js`


Also, show example when nodemon crashes (ex. syntax error)




## (extra) Add nav menu [10m]



## res.json



  ```js
    const pizzasArr = [
        {
          id: 1,
          title: 'Pizza Margarita',
          price: 12,
          imageFile: 'pizza-margarita.jpg',
        },
        {
          id: 2,
          title: "Veggie Pizza",
          price: 15,
          imageFile: "pizza-veggie.jpg"
        }, 
        {
          id: 3,
          title: "Seafood Pizza",
          imageFile: "pizza-seafood.jpg"
        }
    ];
  ```

<!--
@LT: extract this `data/pizzas.json`

Why:
- Same pattern as lab
- It will also help us when we explain req.params and query

-->



## Middleware 

see `Node - Custom Middleware.md`




## JSON Middleware - express.json() [20m]

<!-- Important: instructions in lab "lab-express-basic-server" ask to configure json middleware -->

Configure Express to be able to read incoming HTTP request that contain JSON data in the body.


```js
  // JSON middleware to parse incoming HTTP requests that contain JSON
  app.use(express.json()); 
```

<!-- 
Express < 4.16: body-parser: 
https://medium.com/@mmajdanski/express-body-parser-and-why-may-not-need-it-335803cd048c
-->



## Create repo + upload to Github [20m]
  - Add `.gitignore`
  - Note: mention that if they clone, they'll need to do `npm install`




