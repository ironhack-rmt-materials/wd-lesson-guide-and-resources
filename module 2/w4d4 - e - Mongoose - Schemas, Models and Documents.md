

# Mongoose - Schemas, Models & Documents


<!-- 

Status: summary is complete

Methodology:
- follow lesson on students portal (~~all highlighted~~)
- at the same time, practice all the examples with the students.

-->


Summary:
- Mongoose Schema (what's a schema & how to create it)
- Data Types in Mongoose
- Default value
    ```js
    imageFile: {
        type: String,
        default: 'images/default-image.png'
    }
    ```
- Mongoose built-in validators ("Data types and validation")
  - default, required, enum, min, max...
  - Example: `required`
  - Note: 
    - "The unique Option is Not a Validator. It's a convenient helper for building MongoDB unique indexes"
    - if you modify your model and add/remove `unique`, Mongoose will not take it into account.
    - Solution: drop your DB or reindex (https://github.com/Automattic/mongoose/issues/7396#issuecomment-452905218)


- Custom validation
- Custom setter



- Mongoose methods (follow the cheatsheet)
  - CHEATSHEET: https://gist.github.com/luisjunco/28e17edcc21868753ea6d60983427623
  - Note: for update & delete, start from findByIdAndXXX()


  <!--
  
  @Luis: for codealong, try to do the following:
    - create a product
    - update a product
    - delete a product
    - close connection to DB
    
  -->


- (skip) Utils
- (skip) Mongoose Documents

- (extra) Static vs instance methods
  - https://stackoverflow.com/a/29664606/11298742



- Optional: extract model to specific file
  - why: same pattern as lab + can help us for tomorrow codealong
  - example: https://github.com/ironicHackers-Ironhack-Sept-22/ecommerce-ironic-pizzas/commit/851b985e493bc4920e77f4bb40e55520cb1fb6f8

  