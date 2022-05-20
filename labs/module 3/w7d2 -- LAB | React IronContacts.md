# LAB | React IronContacts

[REPO](https://github.com/ironhack-labs/lab-react-ironcontacts)

[SOLUTION](https://gist.github.com/TA-Remote/e5f4da11cc474ddde14efe537af5ef07)

## Explain:

- fork
- clone

- *in root folder* 
  - npm install
  - npm start


### TIPS:
 - you want to copy the array and create new short array to pass into state
 - in setState always push or sort a copy of array!!!
 - console.log above 'return', or inside functions


#### @TA: check if we showed this syntax in class:

ITERATION 3. UPDATING STATE
    ```
    const getRandomContact = () => {
        const remainingList = [...contactList].slice(5, contactList.length-1);
        let randomContact = remainingList[Math.floor(Math.random()*remainingList.length)];
        return setContacts(contacts => [...contacts, randomContact])
    }
```
ITERATION 4.
    ```
    const sortByAlphabet = () => {
        setContacts(contacts => [...contacts].sort((a,b) => a.name.localeCompare(b.name)))
    }
```