
# Express - Introduction


<!-- 

update m2-m3 swap:

- there's a few new concepts
  - Request Logging
  - Middleware
  - Working with JSON

@todo: review planning & update Demo example.


UPDATE: 
- demo: project-management-server (instead of restaurant)

-->


<!--

- Part 1: some concepts
- Part 2: codealong
  - follow students portal (just changing the topic to a restaurant)

-->


## Part 1: some concepts

- What is a Framework and why we use it

  <!-- @todo: create slides -->

  - Framework vs library:
    - https://www.digitaltechmedia.in/wp-content/uploads/2020/11/framework-vs-library-dtm.jpg
    - https://qph.cf2.quoracdn.net/main-qimg-b21ba6c5e7ab388225dfafa0c96075d5-pjlq
    - (skip) https://kobaltsolutions.com/wp-content/uploads/2021/02/YOUR-CODE.png


- Brief intro to Express.js
  - MERN stack
  - MERN logos: https://miro.medium.com/max/1400/1*FVtCyRdJ6KOr4YswTtwMeA.jpeg


- Refresh HTTP Verbs
  - slides (Refresh "How the internet works"): https://docs.google.com/presentation/d/1-EgP1r7duakjZ6DXfReHIu9cYwEheAWEd_vDL7JtYiU/edit?usp=sharing



## Part 2: codealong (from "Create Express App")

<!-- 

Some notes below (not comprehensive)

Follow students portal.

-->

Methodology:
- create "IronRestaurant" (iron-restaurant)
- we will evolve it during the following days of week 4 (week5 we start using generator)
- sample repo: https://github.com/RemoteRaccoons-Ironhack-Nov-22/ironrestaurant-pizzaForEach/



- Goal today for "IronRestaurant":
    - home
    - contact
    - one image + css
    - nav menu
    - "endpoint" to get a list of pizzas

- (skip) ask students: how do we want to call our pizza company


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
        title: 'Pizza Margarita',
        price: 12,
        imageFile: 'pizza-margarita.jpg',
      },
      {
          title: "Veggie Pizza",
          price: 15,
          imageFile: "pizza-veggie.jpg"
      }, 
      {
          title: "Seafood Pizza",
          imageFile: "pizza-seafood.jpg"
      }
  ];
```


## Middleware 

see `Node - Custom Middleware.md`




## JSON Middleware - express.json() [20m]


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




