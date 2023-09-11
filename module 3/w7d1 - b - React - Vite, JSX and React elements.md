

# React - Vite, JSX and React elements


<!-- Status: complete -->


- Different options to create a React app:
  - Stackblitz
  - Using a toolchain
    https://reactjs.org/docs/create-a-new-react-app.html#recommended-toolchains

Some options to create a React App:
- Online editor
  - stackblitz
  - ...
- Tool
  - Create React App (CRA)
  - Vite
  - Next.js
  - Remix 
  - Gatsby
  - ...

<!--
Legacy CRA:
  - `npx --yes create-react-app react-playground`
-->

- Create app with Vite:
  - `npm create vite@latest react-playground -- --template react`


- Install React Dev Tools 
  https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en



- Explain file & folder structure (for the app we've just created)
  - `package.json`
    - dependencies & dev dependencies
    - scripts: `npm run dev`
      - mention yarn
  - `vite.config.js` config file for Vite (customize Vite, options, plugins etc)
  - `index.html` is the only .html file for the entire React app.
  - `src/main.jsx` file is the default entry point to our React app.
  - `src/App.jsx` root component 




- JSX:
  
  - components: can receive info + return JSX

  - Inside the curly braces, we can put any valid JavaScript expression. 
    - "an expression is a snippet of code that evaluates to a value"
    - (extra) What is a JavaScript Expression? (includes examples, expression vs. statement, etc)
      https://masteringjs.io/tutorials/fundamentals/expressions


  - JSX: must return one parent container


  - Example 1 - embed variables
    
    ```js
      const user = {
        firstName: "bob",
        surname: "smith"
      }
    ```

    ```jsx
      {title}
      <h3>
        Hi, {user.firstName} {user.lastName}!
      </h3>
    ```


  - Example 2 - embed functions (or methods):
      `{firstName.toUpperCase()}`



  - Example 3 - embed function execution
      ```jsx
      function capitalizeFirstLetter(str) {
        return str[0].toUpperCase() + str.slice(1);
      }
      ```

      ```jsx
      return (
        <h1>
          { capitalizeFirstLetter(firstName) }
        </h1>
      )
      ```


  - Example 4: embed the attribute value
    `<div id={theId}>`



  - Example 5 - embed static files: images

    <!-- 
    
    Link to logo

    https://seeklogo.com/images/I/ironhack-logo-F751CF4738-seeklogo.com.png
    
    -->

      ```jsx
      import ironhackLogo from './assets/ironhack-logo.png'; //inside src

      <img src={ironhackLogo} alt="ironhack logo" />
      ```




- (Bonus, self-guided) config JSX autocomplete on VS Code:
  - https://stackoverflow.com/questions/39320393/jsx-or-html-autocompletion-in-visual-studio-code


- Self-closing tags
  ```jsx
  <MyComponent />
  <MyComponent> </MyComponent>
  ```

  Note: self-closing HTML tags (eg. <br />, <hr />, <img />) must always have a closing / to be valid JSX.


- Attributes Names are camelCased
  
  - class —> `className`
  - html attributes are camelCased
    - onlclick —> `onClick`


- (Extra) inline CSS (mention very briefly)
  - For inline css, you will need a JavaScript object with camelCased properties.
  - https://reactjs.org/docs/dom-elements.html#style
  - legacy docs: https://legacy.reactjs.org/docs/dom-elements.html#style


- Comments in JSX
  ` {/* jsx comment */} `


- React Dev Tools

