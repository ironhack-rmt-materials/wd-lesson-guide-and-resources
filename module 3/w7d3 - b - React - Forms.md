

# React - Forms

<!-- 


Status: draft



*** IMPORTANT ***
*** IMPORTANT ***
-
----- Start creating the FORM IN THE SAME COMPONENT WHERE WE HAVE STATE.
-
*** IMPORTANT ***
*** IMPORTANT ***



Steps:
- 1. Create the Form in the same component where we store the list of movies (ie. w/o creating a specific component for the form)

- 2. Creating a specific component for the form (when the user submits, we will need to update state on the parent component -- this is what students find difficult)


Notes:

- Lesson can take much longer than it seems (about 4h)
- Students find it very challenging/confusing (all the part when we need to change state in the parent component etc)

-->


## Step 1: form with 1 field

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


TASK:

- add a new field for "rating"
- (bonus) add a new field for "image Url"
- (bonus) use html form attributes for better ux (required, type=number, min, max...)

Time: 15min




## (Fix) Functionality to delete movies may not work anymore

  If we delete movies based on their id, the functionality to delete may not work.


  Fix: delete movies based on title

  Example: https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/215ee0bbe02603ccf00a918546401a8e02d73c56





## (extra) Handling multiple inputs with a single stateful variable

- IMPORTANT: 
  - Just mention that it is possible 
  - Don't implement it (it takes a lot of time and they had enough concepts)

- See comment here: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec?permalink_comment_id=4246649#gistcomment-4246649



## Step 3: extract to a separate component
- Move the form to a specific component <AddMovie />
- Now we need to pass a callback.


## (extra) Other Fields
- <select>
- <textarea>
- ...

> Google / React docs / Students portal




## (Extra) Searbox:

Functionality for searchbox (asked in today's lab)
- option1: show how to do 
- option2: provide an example with code so that they can see it (ex. in popcorn time)


IMPORTANT: keep searchbar in App.js 
IMPORTANT: keep searchbar in App.js 
IMPORTANT: keep searchbar in App.js 


Example commit 1 (searchbar in App.js): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/e2c1abc8e4ef0217537e30ca07e8a87357e8f49f


Example commit 2 (extract search box to a specific component "SearchBox"): 
- https://github.com/RemoteRaccoons-Ironhack-Nov-22/raccoons-popcorn-time/commit/5f8559833f5d79b08dde32243cb9daafd378f395
- From all possible patterns (without useEffect), keeping a stateful variable "searchQuery" in App.js would be the easiest (otherwise you need to keep a second stateful variable in App.js + update it everytime you add/delete a movie).


Video (web dev simplified):
- https://www.youtube.com/watch?v=E1cklb4aeXA&t=335s


<!--
@todo: record video
- how to implement search box (ex. directly in app.js)
- extract to specific component (ex. "SearchBox" component)
-->


## React Forms Cheatsheet:

Gist: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec

