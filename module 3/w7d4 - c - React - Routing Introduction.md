
# React - Routing Introduction

<!-- 

Status: notes

@todo: improve planning


-->


# Intro

- show examples on some react apps
  - https://meet-them-all.netlify.app/
  - airbnb


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


----------




- Note: show how we can display the nav menu in all pages or only in the homepage



(Follow students portal)


