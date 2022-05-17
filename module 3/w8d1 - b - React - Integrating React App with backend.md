

# React - Integrating React App with backend



<!-- 

status: draft


-->


`npx create-react-app project-management-client`



Methodology:
Offer students these 2 options

- Option 1: 
  - follow students portal (copy code & understand what we do)
  - quicker

- Option 2:
  - Plan the app with students (we have an API, now what functionality we build for the frontend)
  - Implement as much as we have time.
    - feb22: we just had time for:
      - list of projects
      - functionality to create a project
  - This option takes much more time but it's also much more interesting.


<hr />

Hierarchy of components in the students portal:
- ProjectListPage
  - AddProject
- ProjectDetailsPage
- EditProjectPage
- AddTask


<hr />

Feb22:
- We had a hierarchy with all components as direct children of <App />
- Also, we did the call to the API from the top level (in <App>), sending the info down as props (for this exercise is a good option, they can see a different approach + when you create a project they need to call a callback to update the list of projects).





<hr />


May22:

We only had time to implement `<ProjectListPage />`
On the day after, I provided them code to CREATE new project + EDIT a project.
Then, we did the task below


TASK:

0. Initial setup:
- clone repos and run both apps (`npm run dev`, `npm start`)
- server: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-server
- client: https://github.com/Ironborn-Ironhack-March-2022/ironborn-project-management-client

1. Create Project:
- understand the code `<AddProjectPage />` & `<App />`
- Fix: after creating a project, list of projects needs to be updated

2. Edit Project
- understand the code (there's a lot to understand): `<EditProjectPage />`, `<App />`, `<ProjectListPage />`
- Fix: form field `description` is not pre-populated
- Fix: after creating a project, list of projects needs to be updated
- (bonus): if user refreshes the edit page the app may crash or not work as expected. While we don't have the details about a project, we should display a 'loading...' message (conditional rendering) & then, once we receive the data, display the form.

3. Bonus:
- Implement functionality to delete a project 
- Functionality on tasks (ex. create tasks, display list of tasks)


