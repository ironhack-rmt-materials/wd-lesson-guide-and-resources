

# LAB - React IronContacts


How:
- Individual (can also be done in Pairs)


Notes: 
- students find this lab VERY challenging

<!--
@Luis: share the notes below with students, with a note "spoiler alert"
-->






## Iteration 1: component hierarchy


- IMPORTANT: STUDENTS FIND CONFUSING THE EXPLANATION IN ITERATION 1


For the Files:
- You can put all the components in App.js or, if you prefer, you can also create one file per component (as we did in class)


For the Component Hierarchy:

- Choose this option:
  - <App> component (inside that component display all contacts in a <table>, without creating a specific component for the contact).

- Avoid:
  - <App> + <Contact>
  - <App> + <ContactList> + <Contact>
  - Both of them are a great approach (we will take this approach often, when we want something reusable) but, with the things we've learned, if you use this approach the iteration to remove a contact can be more difficult).



## Iteration 1: getting 5 contacts

  ```js
  let fiveContacts = ???; // store the first 5 contacts in this variable
  ```

  ```js
  const fiveContacts = contactsArr.slice(0, 5);
  ```

  Notes: 
  - use `.slice()`
  - avoid `.splice()` (since it mutates the original array, it would lead to unexpected results).


## Iteration 2:

- Emoji: you include emojies directly in your code (copy-paste will work), 🏆


## Iteration 3 | Add New Random Contacts

- The list of contacts now will change (and we need to reflect that in our JSX) → now we need state.


  ```js
  const [contacts, setContacts] = useState(fiveContacts);
  ```


- To add a new contact, avoid mutating the original array.


  BAD:

  ```js

    const myRandomContact = xxx;

    setContacts( (prevValue) => {
        prevValue.push(myRandomContact); //note: push mutates the original array (non-primitive data types are passed by reference).
        return prevValue;
    });
  ```


  GOOD:

  ```js
    setContacts( (prevValue) => {
        const newList = [...prevValue]; //shallow copy
        newList.push(myObject); //we modify the copy (not the original array)
        return newList;
    });
  ```


  EVEN BETTER:

  ```js
    setContacts( (prevValue) => {
        const newList = [myObject, ...prevValue]; //we create a new array
        return newList;
    });
  ```



## Iteration 4 | Sort Contacts by Name and Popularity

- arr.sort() mutates (modifies) the original array
- Remember: we should never update state directly.
- Instead, we should create a copy of the array, for example, with the spread operator (shallow copy):
  
  ```js
    setContacts( (prevContactList) => {
        prevContactList.sort(); //we're modifying state directly
        return prevContactList;
    });
  ```


  ```js
    setContacts( (prevValue) => {
        const copy = [...prevValue]; //shallow copy
        copy.sort( () => {
          // ...
        } )
        return copy;
    });
  ```

- Why: the list of contacts is an array (non-primitive data type)
  - non-primitive data types are passed by reference.



## Iteration 5 | Remove Contacts
- Use id of contact to remove a contact from state
- Passing an argument in onClick: we need an anonymous function
  - `onClick={ () => doSomething("myId") }`




## Common problems

- Adding contacts works but if I click the button very quickly, at some point the application crashes.
  - Possible reason: you may be modifying state directly (if you mutate an array with the previous state, make sure you a copy and mutate the copy)

  