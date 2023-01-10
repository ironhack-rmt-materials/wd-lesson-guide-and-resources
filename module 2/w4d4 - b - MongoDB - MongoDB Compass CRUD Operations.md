
# MongoDB - MongoDB Compass CRUD Operations

<!-- 

- Status: draft (until "## Delete Documents" is ready)

- Methodology: for all the part of operators, rather than explaing one by one
  - explain only the basic concepts (eg. projection)


- @todo:
  - create a cheatsheet with all the different operators & how to use it
  - ask students to do the lab (they'll need to research & apply) 


Note: 
- in the database (IMDB) that we use for this lecture, year is stored as a string. 
- when we make the query, compare with a string (ex. `{year: "2010"}`)


-->

## Intro

- CRUD
  https://i.imgur.com/CRowB2i.png



## Import Data


- We're going to import a DB from IMDB

  1. Download .zip from here: https://s3-eu-west-1.amazonaws.com/ih-materials/learning-units/movies.json.zip
    
    <!--  
      @Luis: 
      - downloaded here: "\Ironhack\misc\backup-imdb-movies"
      - send json directly on ZOOM (sharing on slack sometimes gives problems)
    -->

  2. Import: 
  
    Option 1: use mongoDB compass
      - create db: `cohortname-imdb` + collection `movies`
      - Click on the collection movies + Add Data + Import file

      <!-- @Luis: choose this option (import through Compass) -->

    Option 2: 
      
      ```
      mongoimport --db video --collection movies --file movies.json --jsonArray
      ```
    - Mention: MongoDB comes with a command line tool to import data (eg. JSON, CSV format, etc)


  3. See collection & documents

  4. Navigate to "Schema" tab.
    <!-- LT: demo only (ask students not to do it)  -->
    - there we can find stats of the schema of our documents
    - LT: Update the type of one document (ex. change year to string)
    - takover: *documents of the same collection can have a different schemas*




## Update Documents

- Show how we can do it on Compass:
  - add fields
  - update fields
  - delete fields


## Delete Documents

- Show how to do it on Compass





## Read Documents


<!-- @luis: improve ?? -->


- Query Bar & Filter - Basic Query

{title: "The Godfather"}
{year: "1994"}
{director: "Quentin Tarantino"}



- ObjectId()

{_id: ObjectId('639ae2570db723509c5148f7')}



- Query with Logical Operators: $and, $or, $ne, $nor


{ $or: [ {year: ""}, {year: ""} ] }
{ $or: [ {director: "Francis Ford Coppola"}, {director: "Quentin Tarantino"} ] }


{ $and: [ { year: "2000", rate: "8.5" } ] }

Note: MongoDB provides an implicit AND operation when specifying a comma separated list of expressions.

{ year: "2000", rate: "8.5" }




- Query Projections (specify which fields we want)

{title: 1, year: 1}
{duration: 0, genre: 0}

Advantage: performance (Using projections makes our database queries faster).



- Sort Query Documents

{rate: 1} (ascending)
{rate: -1} (descending)


- Query Documents - Skip & Limit






## Comparison Query Operators



<!-- @luis: improve ?? -->


- (skip) $eq - Equal
- (skip) $ne - Not Equal

- $gt - Greater Than

  {rate: {$gt: "8.5"}}

- $gte - Greater Than Equal

- $lt - Less Than
- $lte - Less Than Equal



## Array Query Operators

$in

{year: { $in: ["1990", "1991", "1992"] } }

$nin

$all



## Element Query Operators

<!-- @todo -->






## Exercise:

- Get all movies released in "2010"
  - Note: year is a string
    <!-- Solution: {year: "2010"} -->

- Get all movies released in "2010" OR "2011"
  - Hint: { $or: [ {field: value}, {field: value} ] }
  - You can also use the $in operator. Ex: {field: { $in: [value1, value2, ...] } }
  <!-- {$or: [{year: "2010"}, {year: "2011"}]} -->


- Get all movies released after 2010 (hint: $gt)
  <!-- {year: {$gt: "2010"}} -->


- From the previous movies, get only `title`, `year` and `rate` 
  - Hint: projection
  <!-- PROYECTION: {title: 1, year: 1, rate: 1} -->

- Sort the previous results by `rate` in descending order
  <!-- SORT: {rate: -1} -->



- Bonus: 
  - Get all "Action" movies with rate above "8.5".
  <!-- 
    {$and: [{genre: "Action"}, {rate: {$gt: "8.5"}}]}
    
    or just:
    {genre: "Action"}, {rate: {$gt: "8.5"}
   -->

  - Get all movies with the genres "Family" AND "Musical" 

  <!--
  
  {$and: [{genre: "Family"}, {genre: "Musical"}]}

  other option:
  {genre: {$all: ["Family", "Musical"]}}
  
  -->





