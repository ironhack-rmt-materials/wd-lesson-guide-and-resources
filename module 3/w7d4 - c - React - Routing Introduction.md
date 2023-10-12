
# React - Routing Introduction

<!-- 

Status: notes

@todo: improve planning (consider adding guided exercise)


React Router Version History (dates on the left):
- https://github.com/remix-run/react-router/releases

Latest cohort:
- June. 2023: v.6.13 (all working good)
- Sept. 2023: v.6.16

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



## (Demo/codealong) Initial Setup + Basic Routing


Notes: 
  - work on "react-characters-app"
  - IMPORTANT: keep the code to display the list of characters in App.js (!!)

Steps:
- install `react-router-dom`
- Render `<BrowserRouter>` in main.jsx
- Add routes

  ```jsx
    <Routes>
      <Route path="/" element={<h1>this is the HOME page</h1>} />
      <Route path="/about" element={<h1>this is the ABOUT page</h1>} />
      <Route path="/contact" element={<h1>this is the CONTACT page</h1>} />
    </Routes>
  ```

- Add nav menu

  ```jsx
    <nav>
      <NavLink to="/">Home</NavLink> |
      <NavLink to="/contact">Contact</NavLink> |
      <NavLink to="/about">About</NavLink> |
    </nav>
  ```



Notes: 
- Show how we can display the nav menu in all pages or only in the homepage
- Explain: Backend vs. Frontend Routes




