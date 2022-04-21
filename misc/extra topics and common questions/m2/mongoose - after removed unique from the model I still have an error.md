
Problem:
- initial Schema with `unique: true`
- I then remove `unique: true` from a field
- When I try to add new documents (eg. with the same name), it keeps complaining that the key is duplicated.


Reason:
- seems like Mongoose uses uniqueness constraint, available natively in indexes.


Solution:
- option1: drop database (you can not do this in production environments)
- option2: `Model.syncIndexes()` 
  - source: https://github.com/Automattic/mongoose/issues/7396