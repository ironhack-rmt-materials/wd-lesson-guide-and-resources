

# Mongoose - Schemas, Models & Documents


<!-- 

Status: summary is complete

Methodology:
- follow lesson on students portal
- at the same time, practice all the examples with the students.

-->


## Mongoose Schema
- what's a schema & how to create it


## Data Types in Mongoose

- String
- Number
- Boolean

- Arrays:
  - ex. array of strings: `ingredients: [String]`

<!-- IMPORTANT: explain/show arrays  -->

All Mongoose types:
  - See students portal: "Supported data types in schemas"
  - Full list: https://mongoosejs.com/docs/schematypes.html


<!--

@Luis: 

make sure we have at least these fields (so that the model is in line with tomorrow's seeds file):

  {
      title: "margarita",
      price: 12,
      ingredients: ["mozzarella", "tomato sauce", "basil"],
      imageFile: 'pizza-margarita.jpg',
  },
-->


## Mongoose built-in validators ('Data types and validation')

<!--
@todo:
- (create cheatsheet)
- introduce a few of them + do an exercise to discover and practice
-->


- Type
  - Show both syntaxes (ie. explain longer syntax)

- `default`
    ```js
    imageFile: {
        type: String,
        default: 'images/default-image.png'
    }
    ```

- `required`


- `unique`
  
  - Note: 
      - "The unique Option is Not a Validator. It's a convenient helper for building MongoDB unique indexes"
      - If you modify your model and add/remove `unique`, Mongoose will not take it into account.
      - Solution: drop your DB or re-index (https://github.com/Automattic/mongoose/issues/7396#issuecomment-452905218)


- `enum`

    ```js
        dough: {
            type: String,
            enum: ["classic", "extra thin", "with cheese", "with garlic"]
        }
    ```

    Example: "with chocolate"


- `min`, `max`


- Others (see students portal)
  - minlength
  - maxlength
  - trim
  - lowercase
  - match
  - validate (Custom validation)
  - set (Custom setter)





## Extract model to specific file
  <!-- @Luis: do this step -->
  - why: same pattern as lab + can help us for tomorrow codealong
  - example: https://github.com/ironicHackers-Ironhack-Sept-22/ecommerce-ironic-pizzas/commit/851b985e493bc4920e77f4bb40e55520cb1fb6f8





## Mongoose methods

- follow the cheatsheet
- CHEATSHEET: https://gist.github.com/luisjunco/28e17edcc21868753ea6d60983427623

- Note: for update & delete, start from findByIdAndXXX()



  <!--
  @todo: create exercise so that they can discover/practice mongoose methods.

  -->


  <!--

  Example:
  - explain methods to Create
  - explain methods to Read
  - ask them to implement updateMany 
    - for all pizzas with price > 12, set a specific "dough"

  -->



## (skip) Close connection to DB

Brief (students can do research)

How: 
- you can use `mongoose.connection.close()`
- but you can only close the connection when you don't need it anymore




## (skip) Other stuff

- (skip) Utils
- (skip) Mongoose Documents

- (extra) Static vs instance methods
  - https://stackoverflow.com/a/29664606/11298742


