
# MongoDB - Introduction

<!-- Status: complete -->


## Intro to DBs and MongoDB


Slides: 

https://docs.google.com/presentation/d/1r3QsTfgXEb0BVd1zN4UXqaYYMIvNoa_vXCq5_VUem-U/edit?usp=sharing




## Interacting with MongoDB
- Command Line
- Using Compass (UI) (we will use compass)



## Compass...

- Open


- Connect (hostname + port)
  - localhost:27017


- Create a Database (ex. school)


- Create Documents
  - create new document with different data types (sting, number, array)
  - fields:
    - title (string)
    - price (number)
    - isVeggie (boolean)
    - ingredients (array)


- Data types in MongoDB:
  - most common: see students portal
  - full list: https://docs.mongodb.com/manual/reference/bson-types/
  - (note: we'll be using Mongoose & data types are a bit different)


- ObjectID
  - it is a unique reference, automatically created when we insert a new document
  - we will use objectID's to identify specific documents


