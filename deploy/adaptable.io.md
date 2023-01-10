# Adaptable (backend deployment)

## At this moment is in BETA (01/11/2022)

### Setting up

1. Ask for an invite code or you can try if they still have an invite code pinned as the first tweet [Adaptable.io Twitter](https://mobile.twitter.com/adaptableio).
2. Click on `+ New App`.
3. Choose `Connect an Existing Repository`
4. Find the GitHub repository of your project.
    1. if you don't find it click on `Add more GitHub repositories`).
    2. Maybe you need to be set as an Owner for the repository.
    3. Try going for the process all over again
5. Choose the branch `main` (or some other branch as `production`).
6. Choose `Express App Template`.
7. Choose `MongoDB`.
8. Select `Next >`. 
<!-- **NOTE: If you have a monorepo you need to change the base director. Your base directory should contain a package.json** -->
9. Choose a name for your application. ex.:`luis-unicorn-farm` **NOTE: This name will be public**.
10. Check the `HTTP Listener on PORT` because we have PORT set as a `.env` variable.
11. Click on `Deploy App`.
12. Create the Runtime Environment => Go to `dashboard` => Click on `Settings` => Create the different variables that you need (should be equal to the `.env`) ex.:
    1. `TOKEN_SECRET`.
    2. `MONGODB_URI`.
    3. Set other variables that you may need for your project.
13. Test if you can access the domain of the backend => `luis-unicorn-farm.adaptable.app`.
    1. If you didn't change the error-handling file and go to the home of your application you'll get:

    ```json
      {
        "message": "This route does not exist"
      }
    ```

    2. If you visit `luis-unicorn-farm.adaptable.app/api` and didn't changed the `index.routes.js` you should see:

    ```json
      "All good in here"
    ```

14. You can test all your endpoints with POSTMAN now.
    1. On postman you should change the `http://localhost:5005` to the `https://luis-unicorn-farm.adaptable.app/`

15. **AFTER FRONTEND DEPLOYMENT**
    1. Create a new `Runtime environment variable` called `ORIGIN`.
    2. Set the value as your deployed frontend URL. ex.: `unicorn-farm.netlify.app`

[GIST](https://gist.github.com/TA-Remote/fa2324189c28491e4f8e16accbc05bf6)