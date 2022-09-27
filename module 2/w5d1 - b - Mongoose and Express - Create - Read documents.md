

# Mongoose and Express - Create - Read documents

<!--

Status: complete.

Slides: "m2w3d3 - Mongoose-and-Express - Basic CRUD"


Methodology:
- do a codealong for all CRUD operations on books
- before each step, analyze with students what we are trying to do and how to solve it


Codealong Final Result (README.md includes all the steps):
- https://github.com/Coding-Ninjas-Ironhack-Sept-2021/mongoose-express-CRUD-codealong

-->


## Intro

- CRUD

- Since today we're just applying existing concepts, some students find it relatively easy + some other students very difficult



## READ: list of books

- route: GET `/books`
- DB query: Book.find
- view: `books/books-list.hbs`


- Remember:
  - place the res.render() method inside the .then()

- Explain Error Handling

    ```javascript
    .catch( (error) => {
          console.log("Error getting list of books from DB", error);
          next(error);
      });
    ```


## READ: book details page

<!--
How: 
  1. think & plan with students
  2. give time to solve individually (15min)
  3. Finally, solve together.
-->

- route: GET `/books/:bookId`
- get book id from `req.params.bookId`
- DB query: Book.findById
- view: `books/book-details.hbs`
- modify the view were we render the list of books (`books/books-list.hbs`), so that we provide a link to see the details of a book.


<!-- @Luis: bonus for advanced students -->
(Bonus) Functionality to filter books by min rating
- Modify route `/books`
- Use query string + method .filter()
- Provide a form so that users can search




## CREATE: create new book

Render Form:
- route: GET `/books/create`
- view: `books/book-create`

Process Form:
- route: POST `/books/create`
- DB query: Book.create()
- view: we will not create a view. Instead, once book is created, Redirect: `res.redirect('/books')`


