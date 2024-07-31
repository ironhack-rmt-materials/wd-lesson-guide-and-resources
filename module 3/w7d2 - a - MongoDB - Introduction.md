
# MongoDB - Introduction

<!-- Status: complete -->


## Intro to DBs and MongoDB


Slides: 

https://docs.google.com/presentation/d/1r3QsTfgXEb0BVd1zN4UXqaYYMIvNoa_vXCq5_VUem-U/edit?usp=sharing


Use cases:
- SQL: finance, e-commerce, transactions (ex. hotel booking)...
- NoSQL: big data, IoT, search engines, social networks...



## Interacting with MongoDB
- Command Line
- Using Compass (UI) (we will use compass)



## Compass...

- Open


- Connect (hostname + port)
  - localhost:27017


- Create a Database (ex. demo-restaurant)
  - collection: "pizzas"



- Create Documents  
  - @LT: use visual interface (so that we can see data types)
  - create new document with different data types (sting, number, array)
  - fields:
    - title (string)
    - price (number)
    - isVeggie (boolean)
    - ingredients (array)

  <!--
  Note: 
  - there's a bug in Compass "Insert not permitted while document contains errors"
  - summary: if you enter the wrong format, Compass will keep showing that error, even after choosing the right format.
  - bug report: https://jira.mongodb.org/browse/COMPASS-3246
  - Quick workaround: click on a different collection & try again
  -->


- Data types in MongoDB:
  - most common: see students portal
  - full list: https://docs.mongodb.com/manual/reference/bson-types/
  - (note: we'll be using Mongoose & data types are a bit different)


- ObjectID
  - it is a unique reference, automatically created when we insert a new document
  - we will use objectID's to identify specific documents


<!-- @Luis: before the break, it can be good to import IMDB -->

