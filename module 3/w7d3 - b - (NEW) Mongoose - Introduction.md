

# Mongoose - Introduction


<!-- 

@LT: 

- instead of iron-restaurant, follow students portal (Books and Authors -- ex. "mongoose-library")

- Students are now quite familiar with Mongoose (did research in mini-project)

- Mini-project research includes:
    - install mongoose
    - create Schema + model
    - connect to DB
    - data types + validators
    - Create + Read (integrated in the routes)

-->


Summary of functionality we'll implement:
- 2 models
    - Pizza
    - Cook
- CRUD Pizza
- Create Cook
- Relations + Populate


Summary of steps:

- install mongoose `npm install mongoose`
- create `/models/Pizza.model.js`
    - example: https://github.com/ironhack-apr2024-theScriptSociety/iron-restaurant/commit/f3c9c97c20cf8f3bcf4d07223f4748691df5203f

- Create `mongoose-playground.js` ?
    <!--
    
    - Advantage: allows to test quickly through the CLI
    - Disadvantage: students are now used to have mongoose methods in the routes.
    
    One option is to create it but only with:
    - mongoose.connect
    - Model.create
    
    -->

- In App.js
    - connect to DB
    - Implement POST /pizzas
        - `Pizza.create()`
        - handle promises with `.then().catch()`

- data types (see students portal)

- mongoose validators

- CRUD in Express
    - Create:
        - `POST /pizzas`
        - test with postman
    - Read:
        - `GET /pizzas`
        - `GET /pizzas/:id` (?)
    - Update: 
        - `PUT /pizzas/:id`
    - DELETE: 
        - `DELETE /pizzas/:id`


- Document Relationships
    - Add 2nd model: `Cook.model.js`
        - name
        - location
        - bio
        <!-- Example: https://github.com/ironhack-apr2024-theScriptSociety/iron-restaurant/commit/9664f5f188f87c1ccfca0556c11627cdfb4ff34f -->
    - Create (2nd model):
        - `POST /cooks`
    - Creating Relationships Between Collections
        - Change pizza schema:
            ```js
                cook: {
                    type: mongoose.Schema.Types.ObjectId,
                    ref: "Cook"
                }
            ```
        - Test with postman: POST /pizzas
    - Populate:
        - Test with postman: GET /pizzas/:id
        - Change endpoint:
            ```js
              Pizza.findById(pizzaId)
                .populate("cook")
            ```

- ...


