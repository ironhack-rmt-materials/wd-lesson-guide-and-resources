

# Mongoose and Express - Update - Delete documents

<!--

Codealong Final Result (README.md includes all the steps):
- https://github.com/Coding-Ninjas-Ironhack-Sept-2021/mongoose-express-CRUD-codealong

-->


## UPDATE

- What do we need? (discuss with students)

- We will need (discussion):
  - Link to "edit"
  - Display a form
    -- this form will need the current information for each book
  - Process form


Steps we will follow:

[ ] Step 1: add link to "Edit"

    /books/:bookId/edit

[ ] Step 2: display form to Edit
    - route (GET  /books/:bookId/edit)
      --> get the details of the book & pass them to the view
    - view

[ ] Step 3: process form
  -- route (POST  /books/:bookId/edit)
  -- redirect




Render Form to Edit:
- add link (eg. in `books-list.hbs`)
- route: GET `/books/:bookId/edit`
- DB query: Book.findById
- view: `books/book-edit`

Process Form:
- route: POST `/books/:bookId/edit`
- DB query: Book.findByIdAndUpdate
  `Book.findByIdAndUpdate(bookId, { title, description, author, rating }, { new: true }).then().catch()`
- view: we will not create a view. Instead, once book is created, Redirect: res.redirect(`/books/${updatedBook.id}`))




## DELETE

Add button to delete:
- in books-list.hbs:

  ```
  <form action="/books/{{_id}}/delete" method="POST">
    <button>Delete</button>
  </form>
  ```

Process Form to DELETE:
- route: POST `/books/:bookId/delete`
- DB query: Book.findByIdAndDelete
- redirect: `res.redirect('/books'))`

