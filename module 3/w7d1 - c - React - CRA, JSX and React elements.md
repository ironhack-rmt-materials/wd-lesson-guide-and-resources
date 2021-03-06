

# React - CRA, JSX and React elements


<!-- Status: complete -->


- Different options to create a React app:
  - Stackblitz
  - Using a toolchain
    https://reactjs.org/docs/create-a-new-react-app.html#recommended-toolchains


- uninstall CRA `npm uninstall -g create-react-app`
  - note: we've tested with CRA install globally vs. not, and takes the same time to create an app.


- Create app with CRA `npx --yes create-react-app my-first-react-app`
  
  Note: `--yes` flag 
  - Appartently in recent versions (I'm using npm v.6.14, students were using npm v.8) (https://stackoverflow.com/questions/69006097/does-npx-no-longer-do-install-less-run)


- (while CRA is installing) Install React Dev Tools 
  https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en


- Explain file & folder structure (for the app we've just created)

  - `public/index.html` is the only .html file for the entire React app.
  - `src/index.js` file is the default entry point to any React app.

  - How we can run our app:
    - `npm start`
    - mention yarn


- JSX:
  
  - components: can receive info + return JSX

  - Inside the curly braces, we can put any valid JavaScript expression. 
    - "an expression is a snippet of code that evaluates to a value"
    - (extra) What is a JavaScript Expression? (includes examples, expression vs. statement, etc)
      https://masteringjs.io/tutorials/fundamentals/expressions


  - JSX: must return one parent container


  - Examples:
    - Example 1 - embed variables
    
    ```
      {title}
      <h3>
        Hi, {student.firstName} {student.lastName}!
      </h3>
    ```


    - Example 2 - embed functions (or methods):
      `{firstName.toUpperCase()}`


    - Example 3 - embed function execution
      ```
      function capitalizeFirstLetter(str) {
        return str[0].toUpperCase() + str.slice(1);
      }
      ```
      ```
      return (
        <h1>
          { capitalizeFirstLetter(firstName) }
        </h1>
      )
      ```


    - Example 4: embed the attribute value
      `<div id={theId}>`



    - Example 5 - embed static files: images
      ```
      import ironhackLogo from './assets/ironhack-logo.png'; //inside src

      <img src={ironhackLogo} alt="ironhack logo" />
      ```



- Self-closing tags
  ```
  <MyComponent />
  <MyComponent> </MyComponent>
  ```
  Note: self-closing HTML tags (eg. <br />, <hr />, <img />) must always have a closing / to be valid JSX.


- Attributes Names are camelCased
  
  - class ???> className
  - html attributes are camelCased
    - onlclick ???> onClick


- Comments in JSX
  ` {/* jsx comment */} `


- React Dev Tools

