
# React - Routing Introduction

<!-- 

Status: notes

@todo: improve planning (consider adding guided exercise)


React Router Version History (dates on the left):
- https://github.com/remix-run/react-router/releases

Latest cohort:
- Apr. 2023: v.6.10 (all working good)
- June. 2023: v.6.13 

-->


# Intro

- show examples on some react apps
  - https://meet-them-all.netlify.app/
  - airbnb


# Cheatsheet

https://gist.github.com/luisjunco/cbd1fe157c7f2f2b6b4983adbea9ae1e



# Slides

<!--

Slides OLD: 
https://docs.google.com/presentation/d/159a7pMKmloZ7-xxamjChtkh6Y2j_I931JJaR9kVVqeU/edit?usp=sharing

@Luis:
- include useful exercises but they're based on react-router v.5.2

-->



# Basic example on Stackblitz

Show basice example on stackblitz
- install `react-router-dom`
- Render `<BrowserRouter>` in index.js
- Add routes

  ```js
    <Routes>
      <Route path="/cats" element={<h2>display list of cats</h2>} />
      <Route path="/dogs" element={<h2>display list of dogs</h2>} />
    </Routes>
  ```

- Add Links

  ```js
  <header>
    <Link to="/dogs">Dogs</Link> |
    <Link to="/cats">Cats</Link>
  </header>
  ```


Final result:
https://stackblitz.com/edit/react-alhmi8?file=src/App.js



Notes: 
- explain what we're trying to achive first
  - install `npm install react-router-dom`
  - <Navigate />
  - ...

- Explain: Backend vs. Frontend Routes




## Old example

Old Initial Code: https://stackblitz.com/edit/react-cucskj?file=src/App.js
Possible final code: https://stackblitz.com/edit/react-bwzc2z?file=src/App.js





# Codealong


- work on "react-characters-app"
- notes: 
  - keep the code to display the list of characters in App.js
  - create 2 components: Home, About
    - update: instead, just display paragraphs.


----------




- Note: show how we can display the nav menu in all pages or only in the homepage



(Follow students portal)


