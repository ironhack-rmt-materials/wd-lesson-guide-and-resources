
# w5d2 Alternative Codealong

<!--

Notes:
- Alternative codealong, for unit "Mongoose and Express - Documents Relationships"
- Students find it challenging when we introduce relationships, references etc
- Explain little by little + provide examples


@todo:
- create seed file with Books + Authors + Relationships (so that we spend less time on that, we could just pass them the seed file and ask them to run it)

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
    - 1:1 → embedded documents
    - 1:many
    - many:many


How to: 
- we will start from yesterday's codealong ("library-project")


Functionality:
- Model for Author (can write multiple books)
- (extra) model for Club (can have multiple authors)




## Steps

 <!-- work in progress -->
 
 <!-- repo: https://github.com/Ironmaidens-Ironhack-Jan-2022/mongoose-express-CRUD-codealong -->



Author model
- Create Author model (so that we can store more information)
- Store relationship (explain why we take this approach)
    `author: {type: Schema.Types.ObjectId, ref: "Author"},`


Add data to DB
- We can update `seed file` to Create Books & Authors
  - for now, we will not store the relationship.
- Store relationships in our DB
  - we can do it manually on Compass for now.


Functionality to display books 
  - We're now displaying the ids, we want to show real info
    `.populate('author')`
  - Note: we need to require the model as well
    `const Author = require("../models/Author.model");`


Functionality to display book details
  - (bonus) display author info instead of id (practice `populate`)



(Optional Exercise) Understand why "Create" does not work

  TASK:
  - try to understand: why functionality to CREATE does not work.
  - discuss: how we could solve it (do not modify code yet)

  How: groups of 2-3
  Time: 15 minutes




Functionality to Create new book
  - When a user tries to create a new book it doesnt work
    - we need to provide a valid objectId
      - (show how it works if the user enters a valid id in the text input)
      - we will need to display some options to let the user choose
        - Add <select> to the form
          - (note: in today's LAB: they can use a select with `multiple`)
        - We will also need to query the DB (`Author.find()`)


Functionality to Display list of authors (READ)
  - for each author, display name, country....


(Super Super Bonus): for each author, display the number of books
- Only for most advanced students
- Interesting patterns:
  - Access data from another .then()
  - .map() and .filter()
  - Compare 2 objectIds (ex. as string)
- IMPORTANT: Takes a lot of time and many students will feel overwhelmed (do not solve in class)
- Possible solution: https://github.com/Ironmaidens-Ironhack-Jan-2022/mongoose-express-CRUD-codealong/commit/31acfad2925040330d83ef92f2654e7113135f17



Other CRUD functionality on Authors
  - CREATE: 
    - apply what we already know
  - UPDATE
    - apply what we already know
  - DELETE
    - more tricky: if we remove an author some things can break in our app.
    - discuss with students


(Bonus) Improve functionality to edit Books
  - At the moment, if we edit the author of a book, we need to enter the id manualy
  - Instead, display a <select>
  - We need to query list of authors + book details (it is a bit tricky, if you use promises with .then() you need to access a varable in a different .then())
  - Option 1: because it is a problem of scope, we can declare a variable in the parent scope (something like this: https://stackoverflow.com/a/28250700/11298742)
  - Option 2: we can use async/await (see the option "ECMAScript 8
" in this answer: https://stackoverflow.com/a/28250697/11298742)

  ```javascript
  router.get("/:bookId/edit", async (req, res, next) => {
      const authors = await Author.find()
      const bookDetails = await Book.findById(req.params.bookId)

      // rest of the magic...

  });
  ```

  <!--

  @Luis: 
  - they will need something very similar for last iteration of today's lab
  - Iteration #10: Editing Movies

  -->




(Super Bonus) Add model Club (a club can have multiple authors)

(Super Bonus) seed file with relationships
  <!-- @luis: if we don't have time to do it, explain a bit -->




