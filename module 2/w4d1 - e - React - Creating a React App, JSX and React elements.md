

# React - Creating a React App, JSX and React elements


<!-- 

Status: complete

@todo:
- simplify & remove anything that is not essential
- too theoretical. It will be do to define a goal (ie. show the design of a simple app) and explain these concepts while we create it.

-->


Some options to create a React App:
- Online editor
  - stackblitz
  - ...
- Tools & frameworks:
  - Create React App (CRA)
  - Vite
  - Next.js
  - Many others (ex. Remix, Gatsby, Astro, ...)


More details:
- https://reactjs.org/docs/create-a-new-react-app.html#recommended-toolchains



Initial Setup:

  <!--

  Gist for students to codealong:
  https://gist.github.com/luisjunco/94492f0a8c7a8d641fff1cdce0f4d4b5
  -->


- open VS Code + a terminal
- navigate to your ironhack directory
- `mkdir module2`
- `cd module2`

- Create app with Vite:
  - option 1: `npm create vite@latest`
  - option 2: `npm create vite@latest react-intro -- --template react`
    - Note: you may be asked for confirmation (Ok to proceed? (y)). In that case, type "y" and hit enter.
    <!-- - source: https://vitejs.dev/guide/ -->
  - `cd react-intro`
  - `code -r .`
  - `npm install`
  - `npm run dev`





## Explain "Ports"

- Similarity: hardware ports
  https://miro.medium.com/max/775/1*OzI8He-ZBEcnrDgV6CLOfw.jpeg

- Common port numbers:
  https://en.wikipedia.org/wiki/Port_(computer_networking)#Common_port_numbers

> A port is a virtual point where network connections start and end. 
> Ports are software-based and managed by a computer's operating system. 
> Each port is associated with a specific process or service.





## Explain file & folder structure
- `package.json`
  - dependencies & dev dependencies
  - scripts: `npm run dev`
    - mention yarn
- `vite.config.js` config file for Vite (customize Vite, options, plugins etc)
- `index.html` is the only .html file for the entire React app.
- `src/main.jsx` file is the default entry point to our React app.
- `src/App.jsx` root component 

  <!-- 
  @todo: 
    - explain npm, dependencies etc.
    - npm scripts ?
  -->

- clean initial code in App.jsx


## Create our first component
  - Create a basic component: `<MyFirstComponent / >` 
  - Optional: create also Header & Footer.
    <!--
    - Note: this is useful so that we keep all the JSX examples inside that a specific component.
    -->


## Practice: create a React component
  <!-- @LT: alternative - create repo with what we have so far & upload to stackblitz (that way, students can see an example) -->
- initial code: https://stackblitz.com/edit/vitejs-vite-waceqd?file=src%2FApp.jsx
- Step 1: create a component Header
- Step 2: render this component in App.jsx
- Bonus: create a component Footer
- Bonus: practice other options for export/import.
- Time: 5min.

- Solution: https://stackblitz.com/edit/vitejs-vite-7zcpti?file=src%2FApp.jsx





## JSX

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



## (Bonus, self-guided) config JSX autocomplete on VS Code:
  - https://stackoverflow.com/questions/39320393/jsx-or-html-autocompletion-in-visual-studio-code



## Self-closing tags

  ```jsx
  <MyComponent />
  <MyComponent> </MyComponent>
  ```

  Note: self-closing HTML tags (eg. <br />, <hr />, <img />) must always have a closing / to be valid JSX.


## (skip for now) Attributes Names are camelCased
  
  - class —> `className`
  - html attributes are camelCased
    - onclick —> `onClick`


## (Extra) inline CSS (mention very briefly)
  - For inline css, you will need a JavaScript object with camelCased properties.
  - https://reactjs.org/docs/dom-elements.html#style
  - legacy docs: https://legacy.reactjs.org/docs/dom-elements.html#style

  ```jsx
    const divStyle = {
        color: "purple",
        border: "1px solid #fff",
        margin: "2em auto",
        padding: "2em",
    }

    return (
      <div style={divStyle}>
      </div>
    )   
  ```



## Comments in JSX
  ` {/* jsx comment */} `


