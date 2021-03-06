

# LAB - React IronContacts


Notes: 
- students find this lab VERY challenging


## Iteration 1:


- IMPORTANT: STUDENTS FIND CONFUSING THE EXPLANATION IN ITERATION 1


For the Files:
- You can put all the components in App.js or, if you prefer, you can also create one file per component (as we did in class)


For the Component Hierarchy:
- Choose this option:
  - <App> component (inside that component display all contacts in a <table>, without creating a specific component for the contact).

- Avoid:
  - <App> + <Contact>
  - <App> + <ContactList> + <Contact>
  - Both of them are a great approach (we will take this approach often, when we want something reusable) but, with the things we've learned, if you use this approach the iteration to remove a contact will be more difficult.



## Iteration 1:

let fiveContacts; // store the first 5 contacts in this variable
const [contacts, setContacts] = useState(fiveContacts);


## Iteration 2:

- Emoji: you can put it directly in your code (will just work), 🏆


## Iteration 4 | Sort Contacts by Name and Popularity

- arr.sort() mutates (modifies) the original array
- Remember: we should never update state directly.
- We need to create a copy of the array, for example, with the spread operator (shallow copy):
  
  ```
    setMovies( (prevValue) => {
        const copy = [...prevValue]
        copy.sort()
        return copy;
    });
  ```

- Why: the list of contacts is an array (non-primitive data type)
  - non-primitive data types are passed by reference.

## Iteration 5 | Remove Contacts
- Use id of contact to remove a contact from state
- Passing an argument in onClick: we need an anonymous function
  - `onClick={ () => doSomething("foobar") }`