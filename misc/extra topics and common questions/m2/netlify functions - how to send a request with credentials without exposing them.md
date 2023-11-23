

# Netlify functions (how to send a request with credentials without exposing them)


## Context

- in m2, we don't have a backend server (we just have our frontend app).

- Sometimes, you may want to connect to an API or service that requires credentials.

- For example, the "OpenWeather API" requires an API key provided in every request:

`https://api.openweathermap.org/data/2.5/weather?lat={lat}&lon={lon}&appid={API key}`


- Usually, you don't want those credentials to be exposed or public.



## Issue

- Since we don't have a backend server, our requests need to be sent from the browser.

- We can store our secret in an environment variable (ex. `VITE_API_KEY`). 
  - This will prevent our key from being exposed on GitHub (as long as .env is in our .gitignore).
  - BUT, we would still be using those credentials from the browser (and, potentially, anyone can see them by looking at the source code from the browser).



## Solution / A better approach

Netlify functions allow you to have code running on Netlify servers.

Instead of sending the requests to our API directly from the browser, we can use that code on Netlify to act as an intermediate step.


The idea is the following:
- Browser sends a request to our code on Netlify (Netlify functions).
- Our code on Netlify sends a request to the API (including the credentials) and we forward the response to the browser.
- Browser receives the response.


## Example

Repo with an example:
https://github.com/ironhack-fulltime-degenerates-oct2023/netlify-functions-demo/

Key files:
- `netlify/functions/api-request-with-credentials.js` (this is the code that we're executing on Netlify servers)
- `netlify.toml` (configuration)


Demo: https://demo-netlify-functions.netlify.app/



<!-- 

For debugging / testing:

- This request will not work: https://api.openweathermap.org/data/2.5/weather?q=amsterdam&appid=${API_KEY}&units=metric

- This request will work: https://demo-netlify-functions.netlify.app/.netlify/functions/api-request-with-credentials

 -->

