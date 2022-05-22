# LAB | Express Spotify

[REPO](https://github.com/ironhack-labs/lab-express-spotify)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/df2a3d70a3b30baa621f81ba3afb20cf)

## INTRO

- make requests to Spotify database and retrieve info about artists, albums etc
- will be using  spotify-web-api-node (npm package)
- use req.query & req.params

### STEPS
- register and get credentials to access Spotify API
	- clientId
	- clientSecret
- ask student to share screen and login etc


Both client id and client secret are used to identify your application. Client id is public information and is ok to show to users. While secret must be kept secret or anyone could potently use your application credentials.

- install dependencies
	- npm install express hbs spotify-web-api-node dotenv
	- dotenv
		- we want to keep so called secrets or some passwords away from the source code
		- we use environment files for that
		- .env file is were we write them. And dotenv package allows us to load files from .env

## TIPS

 1. npm run dev (check in package.json) -> npm start does not work
 2. Form action (in hbs) has to match route (in app.js)
 3. When you receive data from db (in your promise), format data as you need and only then pass into views (suggestion)

@TA:  
show example of console.log when you go into artist's id:
```
app.get("/albums/:artistId", (req, res, next) => {
    spotifyApi
        .getArtistAlbums(here I'll be inserting artist id)
        .then((data) => {
            console.log('>>>>>>>>>>>>>', data.body.items)
            const albumData = {
            albumsArray: data.body.items,
            artist: data.body.items[0].artists[0].name,
            artistId: data.body.items[0].artists[0].id,
        };
```