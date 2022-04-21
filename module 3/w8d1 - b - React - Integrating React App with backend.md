

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

Hierarchy in the students portal:

Components:
- ProjectListPage
  - AddProject
- ProjectDetailsPage
- EditProjectPage
- AddTask


<hr />

Feb22:
- We had a hierarchy with all components as direct children of <App />
- Also, we did the call to the API from the top level (in <App>), sending the info down as props (for this exercise is a good option, they can see a different approach + when you create a project they need to call a callback to update the list of projects).




