
# w5d2 Alternative Codealong

<!--

Notes:
- Alternative codealong, for unit "Mongoose and Express - Documents Relationships"
- Students find it challenging when we introduce relationships, references etc
- Explain little by little + provide examples

 -->



Goals:
- implement document relationships
- populate
- (extra) double populate
- (extra) seed DB with relationships


Intro: 
- Refresh lesson "Data Models"
  - 2 options to store relationships:
    - embedded documents
    - reference
    - for each of those options, (single / multiple)
  - Types of relationships
    - 1:1 --> embedded documents
    - 1:many
    - many:many


How to: 
- we will start from yesterday's codealong ("library-project")


Functionality:
- Model for Author (car write multiple books)
- (extra) model for Club (can have multiple authors)




## Steps

 <!-- work in progress -->
 
 <!-- repo: https://github.com/Ironmaidens-Ironhack-Jan-2022/mongoose-express-CRUD-codealong -->



Author model
- Create Author model (so that we can store more information)
- Store relationship (explain why we take this approach)
    `author: {type: Schema.Types.ObjectId, ref: "Author"},`

Add data to DB
- We can update seed file to Create Books & Authors
  - for now, we will not store the relationship.
- Store relationships in our DB
  - we can do it manually on Compass for now.


Functionality to display books 
  - We're now displaying the ids, we want to show real info
    `.populate('author')`

Functionality to display book details
  - (extra) display author info instead of id (practice `populate`)


Functionality to Create new book
  - When a user tries to create a new book it doesnt work
    - we need to provide a valid objectId
      - (show how it works if the user enters a valid id in the text input)
      - we will need to display some options to let the user choose
        - Add <select> to the form
          - (note: in today's LAB: they can use a select with `multiple`)
        - We will also need to query the DB (`Author.find()`)


Functionality to Display list of authors
  - eg: information that we can get from the Author model
  - (Bonus, very advanced & takes time): for each author, display the number of books


Other CRUD functionality on Authors
  - CREATE: 
    - apply what we already know
  - UPDATE
    - apply what we already know
  - DELETE
    - more tricky: if we remove an author some things can break in our app.
    - discuss with students


(Extra) Add model Club (a club can have multiple authors)

(Extra) seed file with relationships
  - if we don't have to do it, explain a bit



