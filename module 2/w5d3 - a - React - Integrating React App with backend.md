

# React - Integrating React App with backend



<!-- 

status: draft


API_URL: 
- create config/api.js
- declare as const an export/import
- (don't introduce environment variables yet)


Note:
- day is heavy (we see a lot of code).
- try to make it as light & fast as possible

@todo: 
- create quick exercise (e.g. bug hunt with functionality for "Project details page")


repo:
- follow repo from prev. cohort

-->


- navigate to module2 directory
- `npm create vite@latest react-project-management -- --template react`
- cd react-project-management
- code -r .
- npm install
- npm run dev

To run on a specific port:
- npm run dev -- --port=3002





Methodology:


- Option 1: 
  - Self-guided

- Option 2: 
  - follow students portal (copy code & understand what we do)
  - quicker




<hr />

Intro: 
- explain goal + show API endpoints (see Students Portal "Endpoints")
- provide a list of milestones to follow (for each milestone, discuss how to implement it)

Roadmap:
- [ ] Initial setup
      - create app
      - git init
      - cleanup initial code
      - copy index.css (get `index.css` from the students portal)
      - install dependencies (npm install axios react-router-dom)
      - setup routing
      - create `components/Navbar`, `pages/HomePage` and `pages/ProjectListPage`
- [ ] List of projects
- [ ] Create new projects
- [ ] Navbar
- [ ] Project details page
- [ ] Edit projects
- [ ] Delete projects
- [ ] Create new tasks
      - display list of tasks
      - functionality to create tasks
- [ ] (skip) Extracting Components (project card + task card)


Extra:
- show: keep constants in a specific file (e.g. config/api.js)
- show: vs code source control
- show: loader (e.g. https://cssloaders.github.io/)
- mention: toast
  
  <!-- note: demo with an additional state variable "isLoading" -->

  ```jsx
    if (projects === null) {
      return <div className="loader"></div>;
    }

    // or...
    if (projects === null) {
      return <Loader />;
    }
  ```
- show: responsive list of items

Steps (in more detail):
- [ ] Getting Started (initial setup)
- [ ] React Router Setup
- [ ] Project Management API (explains API and available endpoints)
- [ ] Project List Page
      - ProjectListPage.jsx
      - path="/projects"
- [ ] Create Project Page
  - CreateProjectPage.jsx
  - exact path="/projects/create"
  - form
  - POST /projects
- [ ] Project Details Page
  - ProjectDetailsPage.jsx
  - path="/projects/:projectId" 
- [ ] Edit Project Page (form must be pre-populated)
  - EditProjectPage.jsx
  - path="/projects/edit/:projectId"
  - form (pre-populated)
  - PUT /projects/:id
- [ ] Delete the Project 
  - modify EditProjectPage.jsx (add function "deleteProject" + button)
- [ ] Add Task Form
  - to display tasks:
    - `?_embed=tasks`
  - create component `<AddTask>` (form + controlled component)
  - render it in `<ProjectDetailsPage>`
  - modify `AddTask.jsx`:
    - on submit: POST /tasks
      - Note: make sure to pass projectId as a number (passing it as a string will not work)
      - Example: https://github.com/ironhack-fulltime-degenerates-oct2023/codealong-integrating-react-app/blob/86c78481f9c62bdde49ec1eca5f475af1f9d886b/src/components/AddTask.jsx#L15
    - after a task is created, refresh project details: `props.refreshProject();`

- [ ] (skip) Extracting Components (project card + task card)



<hr />


Axios common methods:

- axios.get(url)
- axios.post(url, data)
- axios.put(url, data)
- axios.delete(url)
