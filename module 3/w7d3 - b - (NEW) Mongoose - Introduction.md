

# Mongoose - Introduction


<!-- 

@LT: instead of iron-restaurant, follow students portal (Books and Authors -- ex. "mongoose-library")

-->


Summary of steps:

- install mongoose `npm install mongoose`
- create Pizza.model.js
- create `mongoose-playground.js`
    - connect to DB
    - create our first document: `Pizza.create()`
    - handle promises with `.then().catch()`
    - see examples of other methods (ex. `Pizza.find()`)

- Schema
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
        - `DELTETE /pizzas/:id`


- Document Relationships
    - Create 2nd model: `Cook.model.js`
        - name
        - location
        - bio
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


