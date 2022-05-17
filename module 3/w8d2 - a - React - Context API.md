

# React - Context API



<!-- status: draft -->



## Pre-Setup

Option 1:
`npx create-react-app react-context-api`

Option 2:
- work from this codesandbox:
  https://codesandbox.io/s/relaxed-rumple-vb9p4i?file=/src/App.js



## Intro (slides + students portal)

Slides: Passing information between components
- React data-flow
- Context API
- Redux
https://docs.google.com/presentation/d/1VqmAj_VPWQ2htbWhEXrXT-L1KatZo1FEcixcVyAS2Z4/edit?usp=sharing


Students portal (highlighted)
- prop drilling, etc


## Codealong


- initial code: https://codesandbox.io/s/relaxed-rumple-vb9p4i?file=/src/App.js
  <!-- @Luis: remember to fork !! -->

- explain goal. Demo: https://wnj6h.csb.app/projects/

- ask students to have a look & understand code

- follow students portal (highlighted)

- oficial documentation (highlighted): https://reactjs.org/docs/context.html#reactcreatecontext


- Final result:
  - Possible final result (not finished, only applied to homepage):
    https://codesandbox.io/s/strange-kirch-6hihdd?file=/src/components/Navbar.js:457-503
  - Full result:
    https://codesandbox.io/s/m3-react-context-lesson-code-example-v2-wnj6h?from-embed


## Things to keep in mind

- When does a component re-render ?

  > A component calling useContext will always re-render when the context value changes.
