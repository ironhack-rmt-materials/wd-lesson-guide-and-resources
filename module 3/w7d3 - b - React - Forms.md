

# React - Forms

<!-- 


Status: draft


IMPORTANT:
- Start creating the FORM IN THE SAME COMPONENT WHERE WE HAVE STATE.


Steps:
- Follow same steps we took here (Step 11: Forms): https://github.com/Ironhack-Team-Triangle-July2021/ironhack-cinema/commits/main

- But easier if I break it down in two steps:
  - 1. Create the Form in the same component where we store the list of movies (ie. w/o creating a specific component for the form)
  - 2. Creating a specific component for the form (when the user submits, we will need to update state on the parent component -- this is what students find difficult)


Notes:

- Lesson can take much longer than it seems (about 4h)
- Students find it very challenging/confusing (all the part when we need to change state in the parent component etc)

-->


## Step 1: form with 1 field

- Add form with 1 field (eg. `title`).
  (in the same component were we have state)

- Make it a controlled component (cheatsheet below)

- Process form & add the new movie (only with "Title")

- Clear form upon submission

## Step 2: form with multiple fields

- Add rest of fields to the form
- Add multiple methods to handle changes on each field
  onChange={handleTitle} 
  onChange={handleYear} 
  onChange={handleRating}



## Step 3: extract to a separate component
- Move the form to a specific component <AddMovie />
- Now we need to pass a callback.


## (extra) Other Fields
- <select>
- <textarea>
- ...

> Google / React docs / Students portal



## (extra) Handling multiple inputs with a single method

- Just mention that it is possible (don't implement it, it takes a lot of time and they had enough concepts)

- Main ideas:
  - We store the inputs in an object (instead of separate stateful variables).
  - For the object, we use the same property names as the form fields (so that then we can use `e.target.name` to access object properties dynamically).
  - Spread operator with objects
  - Link: https://stackoverflow.com/a/67234242/11298742


## React Forms Cheatsheet:

- Create the form in our JSX (add onSubmit event & prevent form submission):

    ```jsx

    const handleSubmit = (e) => {
      e.preventDefault();
    }  

    <form onSubmit={handleSubmit}>

    ```

- Make it a "Controlled Component"
  - Initialize state
    `const [title, setTitle] = useState("");`
  - Read the input value from state (ex. `value={title}` )
  - Add onChange event (and update state with the new value)
    <input type="text" name="title" value={title} onChange={handleTitleInput} />

- Handle form submission

- Optional: clear form upon submission

