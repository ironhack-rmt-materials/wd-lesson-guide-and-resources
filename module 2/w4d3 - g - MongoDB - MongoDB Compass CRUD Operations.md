
# MongoDB - MongoDB Compass CRUD Operations

<!-- 

- Status: draft (until "## Delete Documents" is ready)

- Methodology: for all the part of operators, rather than explaing one by one
-- explain only the basic concepts (eg. projection)
-- create a cheatsheet with all the different operators & how to use it
-- ask students to do the lab (they'll need to research & apply) 



Note: 
- in the database (IMDB) that we use for this lecture, year is stored as a string. 
- when we make the query, compare with a string (ex. `{year: "2010"}`)


-->

## Intro

- CRUD
  https://i.imgur.com/CRowB2i.png



## Import Data


- MongoDB comes with a command line tool to import data (eg. JSON, CSV format, etc)

- Syntax (example):

    ```
    $ mongoimport --db users --collection contacts --file contacts.json
    ```

- We're going to import a DB from IMDB

  1. Download .zip from here: https://s3-eu-west-1.amazonaws.com/ih-materials/learning-units/movies.json.zip
  
  2. Import: 
  
    Option 1: use mongoDB compass

    Option 2: 
      ```
      mongoimport --db video --collection movies --file movies.json --jsonArray
      ```

  3. See collection & documents

  4. Navigate to "Schema" tab.
    - there we can find stats of the schema of our documents

    - takover: *documents of the same collection can have a different schemas*




## Update Documents

- Show how we can do it on Compass:
  - add fields
  - update fields
  - delete fields


## Delete Documents

- Show how to do it on Compass




## Read Documents


@todo

<!-- @luis: highlighted -->



## Query Operators


@todo

<!-- @luis: highlighted -->



## Exercise:

- Get all movies released in 2010
- Get all movies released in 2010 OR 2011
- From the previous movies, get only `title`, `year` and `rate` (hint: projection)
- Sort by `rate`


- Get all movies released after 2010 (hint: $gt)


- Bonus: 
  - Get all "Action" movies with rate above 9.
  - Get all movies with the genres "Animation" AND "Family"


