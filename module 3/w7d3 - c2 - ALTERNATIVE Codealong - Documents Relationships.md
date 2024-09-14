
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


<!--
@LT:
- warning: complex concepts
- DO BREAKS OFTEN (short breaks) + quick game after each break (ex. pictionary)
-->



## Explain: Types of relationships

Intro: 
- so far, we have 1 model.
- in our application, we may want to store more complex data 
- Ex. for `author`, we may want to store `name`, `country`, `favFood`...

---


Types of relationships
    - 1:1
    - 1:many
    - many:many


Example of 1:1:
- 1 book --> 1 specs (ex. size, weight, cover img)
- 1 specs --> 1 book

Example of 1:many:
- 1 book --> 1 author
- 1 author --> many books

Example of many:many:
- 1 book --> many authors
- 1 author --> many books



## Explain: options to store relationships:

Options:
  - embedded documents
    - explain with code a example
    - explain multiple embedded documents (array)
    - show example where this may not be ideal (ex. 2 books with same author)
  - reference
      - explain with code a example
      - explain multiple references (array)
  - for each of those options, (single / multiple)


Recommendations (when to use each).



How to: 
- we will start from yesterday's codealong ("library-project")


Functionality:
- Model for Author (can write multiple books)
- (extra) model for Club (can have multiple authors)




## Steps Summary

 <!-- work in progress -->
 
 <!-- 
 
 repo: https://github.com/ironhack-loopey-tunes-may2023/loopey-library-project
 

Note: 
- for error handling, use next(e)

Example:

  .catch( e => {
      console.log("error....", e);
      next(e);
  });

-->



## Author model

- Intro
  - at the moment, we store author as a string (in Book model)
  - but we may want to store more info about authors (ex. country, date of birth...)


- Create Author model
  - example: https://github.com/ironhack-loopey-tunes-may2023/loopey-library-project/blob/main/models/Author.model.js


- Store relationship (in Book model):
  
    ```js
    author: {
      type: Schema.Types.ObjectId,
      ref: "Author"
    },
    ```

  - IMPORTANT: explain why we take this approach


## Compare options to store relationships (1 vs. 2 vs. 3)

Discuss briefly:
- option 1: include a reference in model A
- option 2: include a reference in model B 
- option 3: include a reference in both models (aka Two-way referencing)

Comparison:
- option 3:
  - reading is easier (we just need to read collection)
  - update/delete is more complex (we may need to modify both collections)

Mention: "Single Source of Truth"

Recommendation: single reference.

<!--

More info (do not share with students):
- https://www.mongodb.com/blog/post/6-rules-of-thumb-for-mongodb-schema-design
- section "Intermediate: Two-way referencing"

-->


## Update Seeds file

<!--
@LT:
- add seed w/o relationships + ask students to read understand the code
- (quick demo) show how we could add relationships manually on Compass
- add seed file with relationships + explain (briefly)
-->



- Update `seed file` to Create Books & Authors
  
  - seeds file WITH relationships (`async/await`): https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/main/bin/seeds-with-relationships.js

  Steps:
  - Share code in the live session
  - While they all get the code from the live session, they can have a quick look at the code
  - LT to explain this file



<!--

  OLD: seeds file w/o relationships (`then+catch`): 
  
  https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/main/bin/seeds-without-relationships.js

  In that case, we'd need to store relationships in our DB 
  (for example, manually, on Compass).

-->



- Drop collection + execute seed file

<!--
  @LT: 
  - make commit 
  - introduce VS Code Source Control today
-->


## Fix functionality to display books (fix "READ Books")
  - We're now displaying the ids, we want to show real info
    `.populate('author')`
  - Note: we need to require the model as well
    `const Author = require("../models/Author.model");`



## Practice: .populate()

Fix functionality to display book details (at the moment we're displaying the author's id, we want to display the name)

Note: you'll need to update the route + update the view.

Time: 5min.




<!--
@LT:

  DEMO - from this point, do DEMO (not codealong)

-->


## (Optional Exercise) Understand why "Create" does not work

  TASK:
  - try to understand: why functionality to CREATE does not work.
  - discuss: how we could solve it (do not modify code yet)

  How: groups of 2-3
  Time: 15 minutes




## Fix functionality to Create new book (Fix "CREATE Book")
  - When a user tries to create a new book it doesn't work
    - we need to provide a valid objectId
      - (show how it works if the user enters a valid id in the text input)
      - we will need to display some options to let the user choose
        - Add <select> to the form
        - We will also need to query the DB (`Author.find()`)


  - We need to:
    - modify route GET `/books/create`
    - update view `book-create.hbs`


  IMPORTANT:
  - Mention: in today's LAB, we can use a select with `multiple`.

  <!--
  @LT:
  
  - mention select `multiple`
  - (it's in LAB instructions but worth to mention)

  -->


## Practice: add functionality to display list of authors (READ Author)

  <!--
  Note: if we're short of time, just Demo
  How: in pairs/groups of 3 (since some students may not have code ready)
  -->

  - Desired result: 
    - display list of authors (for each author show: name + country)

  - Steps:
    - create the file `author.routes.js` + mount it in `app.js`
    - in `author.routes.js`, add route `GET /authors`
    - add view `views/authors/authors-list.hbs`


  Example view `authors-list.hbs`:

  ```hbs
    <h1>Authors in our DB:</h1>

    {{#each authors}}
      <section class="author-summary">
          <h2>{{this.name}}</h2>
          <p>
              Country: {{this.country}} <br>
          </p>
      </section>
    {{/each}}
  ```

  Time: 20min.


  Bonus: 
  - add/update navbar
  - add some CSS for the list of authors & the list of books
    - note: to avoid repeating css code, consider creating a generic class (ex. `card`)



## Other CRUD functionality on Authors
  - CREATE: 
    - apply what we already know
  - UPDATE
    - apply what we already know
  - DELETE
    - more tricky: if we remove an author some things can break in our app.
    - discuss with students



## Fix functionality to edit Books (Fix "UPDATE Book") [IMPORTANT: needed for lab iteration #10]

  <!--

  IMPORTANT: 
  - they will need something very similar for last iteration of today's lab
  - Iteration #10: Editing Movies

  - If we don't have time, at least mention & pass them the code.

  -->


  - PROBLEM: at the moment, if we edit the author of a book, we need to enter the id manually
  
  - Instead, display a <select>
  - We need to query list of authors + book details (it is a bit tricky, if you use promises with .then() you need to access a variable in a different .then())
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
   
  To make current author selected (it is a bonus of iteration 10).

  Example commit: 
  https://github.com/ironhack-tech-trash-july2023/techtrash-library-project/commit/97b27f40a2fd9198182a4c305af65eaad45c8f1e

  -->



## (Super Bonus): for each author, display the number of books

<!-- 

IMPORTANT: 
- Only for most advanced students
- Takes a lot of time and many students will feel overwhelmed (do not solve in class)
 -->


- Interesting patterns:
  - Access data from another .then()
  - .map() and .filter()
  - Compare 2 objectIds (ex. as string)
- Possible solution: https://github.com/Ironmaidens-Ironhack-Jan-2022/mongoose-express-CRUD-codealong/commit/31acfad2925040330d83ef92f2654e7113135f17




## (Super Bonus) Add model Club (a club can have multiple authors)



