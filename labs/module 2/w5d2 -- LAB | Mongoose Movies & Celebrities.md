# LAB | Mongoose Movies & Celebrities

[REPO](https://github.com/ironhack-labs/lab-movies-celebrities)

[SOLUTION] (https://gist.github.com/IH-WebDev-TA-Remote/1e6bdf1e493f005fb67c64f82151d444) ?

## INTRO
- create movie + celebrity
- full CRUD on movie
- relationship 1 to many. One movie can have many celebrities, so array of references in the  movie model
- 10 iterations
- instruction is quite detailed! Try not to read it all, and first do it yourself. 


## TIPS
- NO seed file / add to database via form
- don't put all routes in index.js : have movies & celeb routes
- read errors in terminal - very helpful

IN NEW MOVIE HBS:
- in the view you'll need to use html select tag, to list all the celebrities from db
	- in regular input value is what you type there.
	- with select->option, your value is an attribute of option tag. And our value is not the name of the actor , but the reference to that actor (the id)
	
- in movie.routes, if you want to use the model - require it. You will need to get info from db for both movies & celebrities. If you are in movie route, you are not restricted to only use movie model


POPULATE
- use populate method when you want to replace ref with he actual info  
- if you console.log received data you will see you have full information about that movie including celeb details
    ```
    Movie.findById(movieId)
            .populate("cast")
        .then((singleMovieFromDb) => {
        res.render("movies/movie-details", { movie: singleMovieFromDb });
        })
        .catch()
    ```

BONUS:
- Iteration 10 -> trickiest.
    - you want to display one movie details and all the celebrities in the dropdown list.
        - need celeb of specific movie
        - and need all celebs in db
        - Might need two promises
