

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


## READ: list of books

- route: GET `/books`
- DB query: Book.find
- view: `books/books-list.hbs`


- Remember:
  -- It is important to place the res.render() method inside the .then()
  -- error handling


    ```
    .catch( (error) => {
          console.log("Error getting list of books from DB", error);
          next(error);
      });
    ```


## READ: book details page

- route: GET `/books/:bookId`
- DB query: Book.findById
- view: `books/book-details.hbs`



## CREATE: new book

Render Form:
- route: GET `/books/create`
- view: `books/book-create`

Process Form:
- route: POST `/books/create`
- DB query: Book.create
- view: we will not create a view. Instead, once book is created, Redirect: `res.redirect('/books')`


