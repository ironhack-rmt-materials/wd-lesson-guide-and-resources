
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



Create Author model
- Create Author model (so that we can store more information)
- Store relationship
  - `author: {type: Schema.Types.ObjectId, ref: "Author"},`
  - explain why we take this approach

<!-- @Luis:
  compare options to store relationships (1 vs. 2 vs. 3)
 -->


Update Seeds file
- Update `seed file` to Create Books & Authors
  - for now, we will not store the relationship.
  - seeds file:  https://github.com/ironicHackers-Ironhack-Sept-22/ironic-library-project/blob/main/bin/seeds.js
- Drop collection + execute seed file
- Store relationships in our DB (manually, on Compass).

<!-- @todo: update seeds file to create relationships -->



Fix functionality to display books (fix "READ Books")
  - We're now displaying the ids, we want to show real info
    `.populate('author')`
  - Note: we need to require the model as well
    `const Author = require("../models/Author.model");`



Fix functionality to display book details (fix "READ Book Details")
  - display author info instead of id (practice `populate`)
  - time: 5min. (they need to update the route + update the view)



(Optional Exercise) Understand why "Create" does not work

  TASK:
  - try to understand: why functionality to CREATE does not work.
  - discuss: how we could solve it (do not modify code yet)

  How: groups of 2-3
  Time: 15 minutes




Fix functionality to Create new book (Fix "CREATE Book")
  - When a user tries to create a new book it doesnt work
    - we need to provide a valid objectId
      - (show how it works if the user enters a valid id in the text input)
      - we will need to display some options to let the user choose
        - Add <select> to the form
          - (note: in today's LAB: they can use a select with `multiple`)
        - We will also need to query the DB (`Author.find()`)



Add functionality to Display list of authors (READ Author)
  - Desired result: 
    - display list of author. For each author show: name + country
  - How:
    - create `author.routes.js` + mount it in `app.js`
    - in `author.routes.js`, add route `GET /authors`
    - add view `views/authors/authors-list.hbs`



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



## Fix functionality to edit Books (UPDATE Book) [IMPORTANT: needed for lab iteration #10]

  <!--

  IMPORTANT: 
  - they will need something very similar for last iteration of today's lab
  - Iteration #10: Editing Movies

  - If we don't have time, at least mention & pass them the code.

  -->


  - At the moment, if we edit the author of a book, we need to enter the id manualy
  - Instead, display a <select>
  - We need to query list of authors + book details (it is a bit tricky, if you use promises with .then() you need to access a varable in a different .then())
  - Option 1: because it is a problem of scope, we can declare a variable in the parent scope. Example:

    ```js
    router.get("/:bookId/edit", async (req, res, next) => {
      
      let authors;

      Author.find()
        .then( (authorsFromDB) => {
          authors = authorsFromDB; //update variable in the parent scope
          return Book.findById(req.params.bookId); //get book details
        })
        .then( (bookDetails) => {

          // now we have access to bookDetails + authors (both of them are available in the current scope)

          res.render(/*....*/);
        })
        .catch()

    });
    ```

  - Option 2: we can use async/await. Example:

    ```js
    router.get("/:bookId/edit", async (req, res, next) => {
      try {
        const authors = await Author.find()
        const bookDetails = await Book.findById(req.params.bookId)

        //rest of the magic...

      } catch (e) {
        //error handling
      }

    });
    ```

  <!-- 
  
  @Luis: 
  - still missing how to make current author selected (it is a bonus of iteration 10).
  
  -->



## (Super Bonus) Add model Club (a club can have multiple authors)


## (Super Bonus) seed file with relationships
  <!-- @luis: if we don't have time to do it, explain a bit -->





