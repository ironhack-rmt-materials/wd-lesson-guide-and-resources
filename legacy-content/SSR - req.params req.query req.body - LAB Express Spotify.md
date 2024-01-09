
# LAB - Express Spotify

## LAB URL:
- https://github.com/ironhack-labs/lab-express-spotify


## Concepts:
- APIs & Promises
    ```js
    spotifyApi
      .searchArtists()
      .then()
    ```
- req.params
- req.query
- forms
- Handlebars views


Mention:
- Students need a Spotify account (to get credentials)
- We will use a package to interact with spotify API



## Iteration 1 | Spotify API Setup

- We need credentials to interact with Spotify API
  - they will need a Spotify account (or create one if they don't have)
  - IMPORTANT: do this step with all students


- Create a `.env` file and store your credentials

    ```
    CLIENT_ID=your clientId goes here
    CLIENT_SECRET=your clientSecret goes here
    ```

    - Notes:
        - why we use a .env file (store credentials, config. that depends on environment...)
        - .env is added to .gitignore

- Run app:
  - `npm run dev` or `nodemon app.js`





## Extra challenges

- (super bonus): implement pagination (can be a bit tricky, read documentation)

