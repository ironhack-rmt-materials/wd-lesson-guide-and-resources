
# React - Routing Introduction


<!-- 

Status: notes

@todo: improve planning (consider adding guided exercise)


React Router Version History (dates on the left):
- https://github.com/remix-run/react-router/releases

Latest cohorts:
- Feb. 2024: v.6.22 (all working well)
- Aug. 2024: v.6.26

-->



# Intro

- show examples on some react apps
  - https://meet-them-all.netlify.app/
  - airbnb


# Cheatsheet

https://gist.github.com/luisjunco/cbd1fe157c7f2f2b6b4983adbea9ae1e






## (Demo/codealong) Initial Setup + Basic Routing


Notes: 
  - work on "popcorn-time"

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




## Practice: React Router

<!-- 

@todo: 
- improve instructions (more detailed)
- add solutions 
-->

Initial code: https://stackblitz.com/edit/vitejs-vite-bpxr81?file=src%2FApp.jsx

Your task: implement routing.

Bonus: add some nice CSS.

Time: 15min.

<!-- @LT: explain how to do npm install on Stackblitz -->
