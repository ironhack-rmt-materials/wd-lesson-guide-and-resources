

# Netlify functions (how to send a request with credentials without exposing them)


## Context

- in m2, we don't have a backend server (we just have our frontend app).

- Sometimes, you may want to connect to an API or service that requires credentials.

- For example, the "OpenWeather API" requires an API key provided in every request:

`https://api.openweathermap.org/data/2.5/weather?lat={lat}&lon={lon}&appid={API key}`


- Usually, you don't want those credentials to be exposed or public.



## Issue

- Since we don't have a backend server, our requests need to be sent from the browser.

- We can store our secret in an environment variable (eg. `VITE_API_KEY`). 
  - This will prevent our key from being exposed on GitHub (as long as .env is in our .gitignore).
  - BUT, we would still be using those credentials from the browser (and, potentially, anyone can see them by looking at the source code from the browser).



## Solution / A better approach

Netlify functions allow you to have code running on Netlify servers.

Instead of sending the requests to our API directly from the browser, we can use that code on Netlify to act as an intermediate step.


The idea is the following:
- Browser sends a request to our code on Netlify (Netlify functions).
- Our code on Netlify sends a request to the API (including the credentials) and we forward the response to the browser.
- Browser receives the response.


## Example 1 (demo)

Repo with an example:
https://github.com/ironhack-fulltime-degenerates-oct2023/netlify-functions-demo/

Key files:
- `netlify/functions/api-request-with-credentials.js` (this is the code that we're executing on Netlify servers)
- `netlify.toml` (configuration)


Demo: https://demo-netlify-functions.netlify.app/


<!-- 

Example:
- This request will not work: https://api.openweathermap.org/data/2.5/weather?q=amsterdam&appid=${API_KEY}&units=metric
- This request works: https://demo-netlify-functions.netlify.app/.netlify/functions/api-request-with-credentials
 -->



POST requests:
- For a post request, same patterns as get.
- To read from the request body, just use `event.body`.
- Example: https://github.com/Aleale81/netlify-functions-demo/blob/main/netlify/functions/get-city-weather.js

To use dependencies (npm packages):
- Install it in your react app (ie. added to package.json)
- To access those npm packages, using require() in your Netlify Functions.
- More info: https://flaviocopes.com/netlify-functions-npm-packages/


## Example 2

Huetopia:
- https://github.com/Huetopia/Huetopia/blob/main/netlify/functions/api-request-with-credentials.js



## Google Maps JS API


- For google maps api, you need a `<script>` tag in the frontend, including the api key

  - Example: 

    ```jsx
    <script async
        src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap">
    </script>
    ```

  - Documentation: https://developers.google.com/maps/documentation/javascript/overview#Loading_the_Maps_API


- As far as I know, this is the only way to do that (api key needs to be in the browser). For example, airbnb, does it this way at the moment (if you see their source code, you can see their google maps api key).

- more info: https://stackoverflow.com/questions/38153734/do-i-need-to-hide-api-key-when-using-google-maps-js-api-if-so-how


- RECOMMENDATIONS:
  1. Restrict your API keys (for example, by domain)
    - https://developers.google.com/maps/documentation/javascript/get-api-key#restrict_key
  2. Plus, limit the number of requests (so that you don't get a bad surprise)
    - https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps



