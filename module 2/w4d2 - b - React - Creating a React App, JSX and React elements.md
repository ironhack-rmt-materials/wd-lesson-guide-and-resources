

# React - Creating a React App, JSX and React elements


<!-- 

Status: complete

@todo:
- simplify / remove anything that is not essential

-->


Some options to create a React App:
- Online editor
  - stackblitz
  - ...
- Tools & frameworks:
  - Create React App (CRA)
  - Vite
  - Next.js
  - Remix 
  - Gatsby
  - ...


More details:
- https://reactjs.org/docs/create-a-new-react-app.html#recommended-toolchains


<!--
Legacy CRA:
  - `npx --yes create-react-app react-playground`
-->

Initial Setup:
- open VS Code + a terminal
- navigate to your ironhack directory
- `mkdir module2`
- `cd module2`

- Create app with Vite:
  - `npm create vite@latest react-playground -- --template react`

  <!--
  Note: some students get this message:
  - Need to install the following packages
  - Ok to proceed? (y) -- Type "y"
  -->


  <!-- 
  @todo: 
    - explain npm, dependencies etc.
    - npm scripts ?
  -->

Explain file & folder structure (for the app we've just created):
  - `package.json`
    - dependencies & dev dependencies
    - scripts: `npm run dev`
      - mention yarn
  - `vite.config.js` config file for Vite (customize Vite, options, plugins etc)
  - `index.html` is the only .html file for the entire React app.
  - `src/main.jsx` file is the default entry point to our React app.
  - `src/App.jsx` root component 




- Install React Dev Tools 
  https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en




Creating our first component:
  - Create a basic component: `<MyFirstComponent / >` 
    <!--
    - Note: this is useful so that we keep all the JSX examples inside that a specific component.
    -->


JSX:

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



  - (skip) Example 3 - embed function execution
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


  - Example 4: function that returns JSX

      ```jsx
      function renderTitle() {
        return <h1>this is a title</h1>;
      }
      ```

      ```jsx
      return (
        <>
          renderTitle()
        </>
      )


  - (skip) Example 5: embed the attribute value
    `<div id={theId}>`



  - (skip) Example 6 - embed static files: images

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


