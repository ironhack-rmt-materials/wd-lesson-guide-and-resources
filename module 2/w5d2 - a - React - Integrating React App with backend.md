

# React - Integrating React App with backend



<!-- 

status: draft


-->


- `npm create vite@latest integrating-react-app -- --template react`





Methodology:


- Option 1: 
  - Self-guided

- Option 2: 
  - follow students portal (copy code & understand what we do)
  - quicker




<hr />

Intro: 
- explain goal + show API endpoints
- provide a list of milestones to follow (for each milestone, discuss how to implement it)

Summary of steps:
- [ ] Getting Started (initial setup)
- [ ] React Router Setup
- [ ] Project Management API (explains API and available endpoints)
- [ ] Project List Page
- [ ] Create Project Page
  - component + render it in App.jsx
  - form
  - POST /projects
- [ ] Project Details Page
- [ ] Edit Project Page (form must be pre-populated)
  - component + render it in App.jsx
  - form (prepopulated)
  - PUT /projects/:id
- [ ] Delete the Project 
- [ ] Add Task Form
  - form
  - POST /tasks
  - Note: make sure to pass projectId as a number (passing it as a string will not work)
  - Example: https://github.com/ironhack-fulltime-degenerates-oct2023/codealong-integrating-react-app/blob/86c78481f9c62bdde49ec1eca5f475af1f9d886b/src/components/AddTask.jsx#L15
- [ ] Extracting Components (project card + task card)



<hr />


Axios common methods:

- axios.get(url)
- axios.post(url, data)
- axios.put(url, data)
- axios.delete(url)
