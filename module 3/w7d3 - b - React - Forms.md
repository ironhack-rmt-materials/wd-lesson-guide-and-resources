

# React - Forms

<!-- 


Status: draft


IMPORTANT:
- Start creating the FORM IN THE SAME COMPONENT WHERE WE HAVE STATE.


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



## React Forms Cheatsheet:

Gist: https://gist.github.com/luisjunco/6c59bc3ea6a1d0b3a975d15ff2115fec

