

# React - Context API


<!-- status: draft -->

<!-- 

@todo: 
- create cheatsheet
- create repo to fork (for codealong)


-->




## Intro (slides + students portal)

Slides: Passing information between components
- https://docs.google.com/presentation/d/1VqmAj_VPWQ2htbWhEXrXT-L1KatZo1FEcixcVyAS2Z4/edit?usp=sharing
- topics: props drilling, context API, Redux




## Syntax Intro

@todo:
- create a demo with the basic syntax (without wrapper component etc)

<!-- - Initial code:
  - 3 components in the same file: Parent, Child, GrandChild
  - https://codesandbox.io/s/beautiful-khorana-2pqxg4?file=/src/App.js

- (quick refresh) Show prop drilling:
  - declare a variable in Parent component: `const language = "Spanish";`
  - pass that variable to GrandChild using props drilling.

- Show Context API syntax:

  1. Create the context with `createContext()`

    ```js
    import { createContext } from "react";
    const LangContext = createContext("en"); //as an argument, you can pass default value

    function Parent() {
      //...
    }

    ```

  2. Use the context 

    ```js
    import { useContext } from 'react';

    //import { LangContext } from './LangContext.js';

    //...

    function GrandChild() {
      const lang = useContext(LangContext);
      
      //...
    }


    ``` -->



ex. in `index.js`

  ```js
    <LanguageContext.Provider value="sp">
      <App />
    </LanguageContext.Provider>
  ```



## Codealong


- Initial code - Option 1 - Stackblitz:
  - https://stackblitz.com/edit/vitejs-vite-kx7enk?file=src%2FApp.jsx
    <!-- @LT: remember to fork !! -->

- Initial code - Option 2 - fork from Github:
  - https://github.com/ironhack-rmt-resources/react-context-api-demo
    <!-- @LT: remember to fork !! -->



- explain goal. Demo: https://wnj6h.csb.app/projects/

- ask students to have a look & understand the initial code

- initial intro to the syntax:
  - Here, in index.js we provide the context
  - ...and in ProjectCard.js we consume it.
  - Basic syntax intro: https://codesandbox.io/s/fancy-rain-fyzklj?file=/src/index.js

- follow students portal
  - 2 steps: providing context + consuming

- documentation:
  - (old): https://reactjs.org/docs/context.html#reactcreatecontext
  - (new) https://react.dev/reference/react/useContext

- Final result:
  - Possible final result (not finished, only applied to homepage):
    https://codesandbox.io/s/strange-kirch-6hihdd?file=/src/components/Navbar.js:457-503
  - Full result:
    https://codesandbox.io/s/m3-react-context-lesson-code-example-v2-wnj6h?from-embed


## Things to keep in mind

- When does a component re-render ?

  > A component calling useContext will always re-render when the context value changes.

