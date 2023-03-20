

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




## IronLauncher


- Setup your project (with NPX):

    ```
    npx --yes ironlauncher library-project
    ```

    Choose:
    - `Views`
    - `No auth`

    <!-- 

    @Luis: 
      - create with auth & just go through the code ??
      - (instead of auth codealong)

    -->


    Note: ironlauncher automatically creates a folder with the name of the app.


- Explain `npx` (vs. npm install)

- Explain...
  - Open `package.json` & explain scripts (start / dev)
  - run: `npm run dev`
  - Opinionated (dependencies + structure)
    - we could use other packages
    - the structure created by the generator is just one of many ways to structure Express apps
  - dependencies
  - general folder structure (`/models`, `/routes`, `/views`)
  - .env & environment variables
    <!-- IMPORTANT: explain `environment variables` here -->
  - .gitignore
  - general flow of the application (starting from server.js)
  - error handling
  - express.Router (create mountable route handlers)
    - https://expressjs.com/en/guide/routing.html#express-router
    - show how we can add more routes



> The app structure created by the generator is just "one of many ways" to structure Express apps.



## Fix: ironlauncher not installing dependencies:
```
npm i cookie-parser@1.4.6 dotenv@16.0.3 express@4.18.2 hbs@4.2.0 mongoose@7.0.2 morgan@1.10.0 serve-favicon@2.5.0
```

```
npm i nodemon@2.0.21 --save-dev
```



## Flags (options)

- See documentation: https://www.npmjs.com/package/ironlauncher




## Creating our first app

- Goal: we're going to create an app for a Library (we'll have CRUD functionality for books)

- Start VS Code live session


### Adding the model

- Add Book model (students portal: 'Adding the model')
  `models/Book.model.js`

  - IMPORTANT: follow the same model as students portal (so that we can use seed file later)


### Seed File

- Create seed file (students portal: 'Creating a seed file')
  - Explain: What is a seed file + why it is useful
  - Add the code or codealong (`/bin/seeds.js`)
  - Run seed file (`$ node bin/seeds.js`)
  - Check data is loaded (Compass)

  
<!--
@Luis: drop DB library-project (from previous cohorts)
-->

