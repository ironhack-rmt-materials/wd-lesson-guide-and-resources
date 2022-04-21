

# Express - Express Generator


Summary:
- what is a generator
- ironlauncher
  - what it is
  - how to setup
  - understand how it works
- seed file




## Intro

- when building new applications, we repeat a lot of the work (especially for the initial setup)

- IronLauncher
  - npm package (https://www.npmjs.com/package/ironlauncher)
  - Opinionated:
    - dependencies
    - structure (the structure created by the generator is just one of many ways to structure Express apps)




## IronLauncher


- Setup your project (with NPX):

    ```
    npx ironlauncher library-project
    ```

- Explain `npx` (vs. npm install)

- Explain...
  - Open package.json & explain scripts (start / dev)
  - run: `npm run dev`
  - dependencies
  - general folder structure
  - .env & environment variables
  - .gitignore
  - general flow of the application (starting from server.js)
  - error handling
  - express.Router (create mountable route handlers)
    - https://expressjs.com/en/guide/routing.html#express-router
    - show how we can add more routes



> The app structure created by the generator is just "one of many ways" to structure Express apps.




## Flags (options)

- See documentation: https://www.npmjs.com/package/ironlauncher




## Creating our first app

- Goal: we're going to create an app for a Library (we'll have CRUD functionality for books)

- Add Book model (students portal: 'Adding the model')
  `models/Book.model.js`

  - IMPORTANT: follow the same model as students portal (so that we can use seed file later)


### Seed File

- Create seed file (students portal: 'Creating a seed file')
  - Explain: What is a seed file + why it is useful
  - Add the code or codealong (`/bin/seeds.js`)
  - Run seed file (`$ node bin/seeds.js`)
  - Check data is loaded (Compass)

  