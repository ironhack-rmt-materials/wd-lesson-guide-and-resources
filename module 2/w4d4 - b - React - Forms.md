

# React - Forms

<!-- 


Status: draft



*** IMPORTANT ***
*** IMPORTANT ***
-
- Start creating the FORM IN THE SAME COMPONENT WHERE WE HAVE STATE.
-
*** IMPORTANT ***
*** IMPORTANT ***



Steps:
- 1. Create the Form in the same component where we store the list of movies (ie. w/o creating a specific component for the form)

- 2. Creating a specific component for the form (when the user submits, we will need to update state on the parent component -- this is what students find difficult)


Notes:

- Forms can take much longer than it seems (!!).
- Students find it very challenging/confusing (all the part when we need to change state in the parent component etc)

-->


## Step 1: form with 1 field

- In the component where we have the list of movies:
  - Create a `<section>`

- Add form with 1 field (eg. `title`).
  (IMPORTANT: in the same component were we have state)

- Make it a controlled component (cheatsheet below)

- Process form & add the new movie (only with "Title")


  ```js
    const newMovie = {
      title: title 
    };

    setMovies( (prevMovies) => {
      return [newMovie, ...prevMovies];
    });
  ```


- Clear form upon submission

  ```js
    setTitle("");
  ```




## Step 2: form with multiple fields

Practice: React Forms

- Add a new field for "rating"
- (Bonus) Add a new field for "image Url"
- (Bonus) Research/apply html form attributes to improve user experience (required, type=number, min, max...)

Time: 15min




## (Extra) Handling multiple inputs with a single stateful variable

<!--
- Just mention that it is possible 
- Don't implement it (takes a lot of time)
-->

See comment here: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec?permalink_comment_id=4246649#gistcomment-4246649




## (Fix) Functionality to delete movies may not work as expected

<!--
How to reproduce:
- Create 2 new movies
- Delete one of them
-->

If we delete movies based on their id, the functionality to delete may not work.


Fix: generate a unique id each time a movie is added
- In order to do that, we can find out the max id in the array of movies.

<!-- 

@update: 

generate a unique id (will make our life easier when we implement routing)

-->


Exercise: 
- Find max in array of numbers + array of objects
- note: do some research
- Instructions: https://stackblitz.com/edit/js-wjdmct?file=index.js
- Solution: https://stackblitz.com/edit/js-miexdw?file=index.js

- Time: 12min.



Possible solution:

```js
  const addNewMovie = (newMovie) => {
    // find out id for the movie that we want to add
    const movieIds = moviesToDisplay.map(function (elm) {
      return elm.id;
    });
    const maxId = Math.max(...movieIds);
    const nextId = maxId + 1;

    // prepare an object with the details of the new movie (inc. the id)
    const movieDetails = {
      ...newMovie,
      id: nextId
    }

    const newList = [movieDetails, ...moviesToDisplay];
    setMoviesToDisplay(newList);
  }
```






## Step 3: extract to a separate component [30min.]

<!-- 

@LT: 

- takes a bit longer than it seems, but helps refresh patterns we've seen today (ex. passing callback) 

- alternative: implement it over a break (10min) & explain the final code.


- update: needed for lab ? if not, can also be done tomorrow.

-->

- Move the form to a specific component <AddMovie />
- Now we need to pass a callback.



## (extra) Other Fields
- <select>
- <textarea>
- ...

> Google / React docs / Students portal




## (Extra) SearchBox:




<!--
@todo: record video
- how to implement search box (ex. directly in app.js)
- extract to specific component (ex. "SearchBox" component)

- or, share link to youtube.

-->



Functionality for searchbox (asked in today's lab)
- option1: show how to do 
- option2: provide an example with code so that they can see it (ex. in popcorn time)
- option 3: pass video
  - Implement search filter (web dev simplified, 14min.): https://www.youtube.com/watch?v=E1cklb4aeXA&t=335s


<!-- IMPORTANT: keep searchbar in App.js  -->
<!-- IMPORTANT: keep searchbar in App.js  -->
<!-- IMPORTANT: keep searchbar in App.js  -->



Example commit 1 (searchbar in App.js): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/e2c1abc8e4ef0217537e30ca07e8a87357e8f49f


Example commit 2 (extract search box to a specific component "SearchBox"): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/5f8559833f5d79b08dde32243cb9daafd378f395
- From all possible patterns (without useEffect), keeping a stateful variable "searchQuery" in App.js would be the easiest (otherwise you need to keep a second stateful variable in App.js + update it everytime you add/delete a movie).




## React Forms Cheatsheet:

Gist: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec

