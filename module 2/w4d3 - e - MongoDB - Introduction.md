
# MongoDB - Introduction

<!-- Status: complete -->


## Intro

- What is a database
  - it's a program we use to save data and/or retrieve data
  - note that until now, every program that we wrote will reset/refresh every time we run it (variables will lose its value)


- Advantages vs. sharing on a text file (show on students portal):
  - Reliability (data can always be accessed)
  - Efficiency (we could just use files to store the data, but this solution will be slow for any serious program)
  - Scalability
  - Concurrency (multiple clients/machines connected to our database simultaneously)
  - Data abstractions (we can store data using complex data types)
  - Query language (makes easier to read/write data)



- Relational vs non-relational

  - Just mention those two categories (do not get into detail)

  https://uploads-ssl.webflow.com/5d367dcf0ec6034477e114ae/608b38afa457656b9f29dc4f_database%20vs%20categories%2002.png

  https://assets-global.website-files.com/5ec7dad2e6f6295a9e2a23dd/5ee016f44336f8b9a40aa050_relational-vs-nonrelational-databases.png

  https://www.ithinkupc.com/media/legacy/Web/images/blog/sql-nosql-esquema-base-datos.png


- (meme) "no-sql"
  - the coding love (https://thecodinglove.com/when-the-sales-guy-tells-us-the-project-doesnt-need-any-database-because-the-client-said-nosql)



## Intro to mongo

- non-relational DB

- stores data in databases > collections > documents > fields
  - https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_157ca84354e93013a2289e0e4a8809a6.png

- JSON-like format

- why mongo


## Interacting with MongoDB
- Command Line (self-guided)
- Using Compass


## Compass...

- Open


- Connect (hostname + port)


- Create a Database


- Create Documents
  - create new document with different data types (sting, number, array)


- Data types in MongoDB:
  - most common: see students portal
  - full list: https://docs.mongodb.com/manual/reference/bson-types/
  - (note: we'll be using Mongoose & data types are a bit different)


- ObjectID
  - it is a unique reference, automatically created when we insert a new document
  - we will use objectID's to identify specific documents


