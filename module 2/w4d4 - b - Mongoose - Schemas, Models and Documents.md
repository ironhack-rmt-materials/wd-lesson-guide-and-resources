

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
    ```
    avatarUrl: {
        type: String,
        default: 'images/default-avatar.png'
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



- Mongoose models
  - Create: 
    - `Model.create(data)`
    - `Model.insertMany(arr)`
  - Read
    - `Model.find()`
    - `Model.find({price: {$gt: 20} })`
    - `Model.findOne()`
    - `Model.findById()`
  - Update:
    - `Model.updateMany()`
    - `Model.updateOne()`
    - `Model.findByIdAndUpdate()`
    - NOTE: will return the original document (not the updated)
      - Can pass options: https://stackoverflow.com/a/43474183/11298742
  - Delete:
    - `Model.deleteMany()`
    - `Model.deleteOne()`
    - `Model.findByIdAndRemove()`


- (skip) Utils
- (skip) Mongoose Documents

- (extra) Static vs instance methods
  - https://stackoverflow.com/a/29664606/11298742

  