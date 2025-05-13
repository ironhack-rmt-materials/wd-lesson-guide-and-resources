# Netlify Deployment (frontend)

## Setting the React

1. Create an account
2. Click on `Import from Git` => Click on `GitHub`
3. Authorize => Choose where you have the GitHub repository (your personal GitHub or the organization where the project lives)
4. Select where that repository lives (Personal / Organization) => Search for the GitHub repository name e.g.: `luis-unicornfarm-client` **NOTE: You may need to add the organization on the dropdown menu (`add another organization`)**
5. Select the branch that you'll be your production build. e.g.: `main` or `production`
6. Your deploy probably will fail at that point. Let's set the environment variables
    1. Go to `Site Settings`
    2. Click on `Build & Deploy`
    3. Click on `Enviroment`
    4. Click on `Edit Variables`
    5. Create one with the `key = CI` and the `value = false`
    6. Create one for the `REACT_APP_API_URL` and the value should be the URL from the REST API that you created and deployed (the pattern should be the same as you set on the REACT app, if you finish with a slash, finish with a slash.... If you don't have the slash, don't use a slash on netlify).
    7. Set other variables that you may need for your project.
7. Changing API connection on React
    1. If you don't have it already, create a `.env` file
    2. Create the variable `REACT_APP_API_URL` and set the value as the `http://localhost:5005` (or the localhost that you backend is running on)
    3. Change your Axios (or fetch) requests to use the `process.env.REACT_APP_API_URL`
    4. Kill the terminal process, run it again (`npm start`) and test the React Application on the local environment
    5. Make a commit and push it
8. Click on `Domain management`
    1. On Custom domains => Click on `options` => Click on `edit site name`
    2. Choose a name for your application e.g.: `unicorn-farm` **NOTE: This will be public for sure**
9. We need to set the CORS policy on our backend to accept the frontend to make requests
    1. Go to the service you used to deploy your backend and create a variable `ORIGIN`
    2. Set the value as the URL for your deployed frontend. e.g.: `unicorn-farm.netlify.app`
    3. You might need to clear the cache for that to work
10. To ensure a better user experience we need to set the redirects for netlify
    1. Create a file called `_redirects` on the folder `Public` of your React application.
    2. Use the code `/* /index.html 200`

[Gist](https://gist.github.com/TA-Remote/67e617f725bbb68f67d534d162c1bc5f)