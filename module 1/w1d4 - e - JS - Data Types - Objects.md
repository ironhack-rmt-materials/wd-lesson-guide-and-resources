

# JS - Data Types in JavaScript - Objects

<!--- 
Status: draft

-->





## Intro:

- Array & Objects: 2 ways of organizing information (more on that in a moment: "Why we use objects")

- Object = collections of properties 
- key-value pair
- keys are unique (one key will always have just one value associated to it)
- "Dictionary"

- example:

  ```
  let user = {
    key1: value,
    key2: value,
    key3: value
  };
  ```

- Data types: we can store any valid data type


## Why we use objects

- group values that belong together
- relationships between variables

- Arrays vs Objects
  - both of them are useful to group information (collection of things)
  - arrays: (usually) elements with the same relationship
    - ex: array of students
    - ex: array of teachers
    - ex. array of numbers
  - objects: store elements with a different relationship (relationship between the variable and the value)
    - company object (founder, marketing director, front-end developer, ...)
    - company 2 (founder, website, email, number of employees)


  Example 1:

  ```javascript  
  const employees = ['alice', 'bob', 'charly'];

  const company = {
    director: 'alice',
    pm: 'bob',
    develor: 'charly',
  };
  ```



  Example 2:

  ```javascript  
  const userDetails = ['bob', 20, 'bogotá', false];

  const user = {
    fullName: 'bob smith',
    age: 20,
    city: 'Bogotá',
    isLoggedIn: false,
  };
  ```



## How to create an object:


Object literal syntax

    ```
    let someObject = {
        key1: value,
        key2: value,
        key3: value
    };
    ```

Object constructor syntax (skip)

  ```
	let someObject = new Object();
  ```


## Accessing the values
- dot notation
- square bracket notation (with a string inside brackets)


- dot notation vs bracket notation
  - in most cases we use dot notation (more simple and easier to read)
  - you may need bracket notation for:
    - access keys with multiple words (`myObj["marketing manager"]`)
    - access keys with dynamic names (`myObj[myVariable]`)



## Add properties (dot notation / bracket notation)

- dot notation
- bracket notation


## Update properties (dot notation / bracket notation)



## Remove properties (delete operator)

    ```
	delete olympicRecords.doubleOllie;	// dot
	delete olympicRecords['doubleOllie'];	// bracket
    ```


// (Break)


##  Check if a property exists (in operator)
	
    ```
        let myCar = {
            make: 'Honda',
            model: 'Accord',
            year: 1998
        };

        'make' in myCar; // returns true
        'model' in myCar; // returns true
    ```
        


## List properties
- Object.keys(myObj) 
  - returns and array (we can then loop through the array etc)


## List values
- Object.values()
  - returns an array


## Loop through objects

- We can loop through the array returned by Object.keys()
- We can loop through the array returned by Object.values()


- for ... in loop

    ```
	for (let record in olympicRecords) {
	  console.log(record)
	}
    ```


// (Break)


## Declaring an object with CONST
- we can add/update/delete properties
- but we can not reassign the object
    - is fixed to the same reference (address) in the memory
    - the variable declared with const can’t be reassigned to a different value


    > In the case of declaring an object using the const keyword, this means that new properties and values can be added BUT the value of the object itself is fixed to the same reference (address) in the memory and the object (or any variable declared with const) can’t be reassigned.



## CHECK FOR UNDERSTANDING

<!-- 
GOAL: practice objects + get a nice name for our class ;)
TIME: 15m + 10m
-->

- Create an object to store information of our class:
  - location ("remote")
  - field ("web dev")
  - array of students (at least some)
- Later in the code, add a new property "cohortName" (choose a cool name for our class)
- Update field ("full-stack")
- Bonus: create a function that receives an object with the details of a class & displays the name of each student.
- (bonus) how about we want to store info about our students? in the next lesson we will learn how to work with more complex data structures


  <!--
  @Luis:
  - take the opportunity to choose a name for our class
  -->



## Extra resources

- Summary / Sample code:
  https://stackblitz.com/edit/js-jcxkmx?file=index.js



