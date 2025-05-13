

## Unique is... 'unique'


Summary:
- "MongoServerError: E11000 duplicate key error" after Removing "unique: true"


Problem:
- At some point, we were using `unique: true` in a Schema.
- Then we removed `unique: true` from a field.
- Now I try to add new documents (eg. with the same name), and I keep getting the following error:

> E11000 duplicate key error collection


Reason:

- "The unique option for schemas is 'not' a validator. It's a convenient helper for building MongoDB unique indexes"

- In plain English: `unique` doesn't work like other Mongoose built-in validators like required, default, enum, min, max etc. Instead, it relies on MongoDB functionality (you can remember this by thinking that "unique is... unique").


- More info: https://github.com/Automattic/mongoose/issues/7396


Solution:

- option 1 (if you can drop the collection)
  - Drop the collection on which you were using unique.
  - This is the easiest option, as long as you can drop the collection or DB (eg. if you're in development and you don't have valuable data... or if you're in production and you don't like your job).

- option 2: 
  - Execute `Model.syncIndexes()` 
  - More details: https://mongoosejs.com/docs/api/model.html#Model.syncIndexes
  

