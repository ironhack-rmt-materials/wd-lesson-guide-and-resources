
# w8d1

<!-- 

  @todo:
  - improve this notes for day planning

 -->


- Project 3: 
  - Show 2 examples of m3 projects.
  - They can start thinking what they want to build



- (OLD) Refresh React concepts:
  - can be done in pairs (45m+15m) or all together (30m.)
  https://docs.google.com/document/d/1D20pulIvbXX70ljTCDvMj4wZyvCpM1ggGgZAZj-Nr7I/edit?usp=sharing



- Refresh:
  - useEffect & API calls
  - POST request to create a resource.


- Intro:
  - show architecture module 3 (react app + api)
  - plan for the day


- Run Commands:

  <!--
  Update Jan 2023:
  
  - we could now use "npx ironlauncher@latest new-app --fs"

  - it will create 2 directories with server + client
  - server: includes auth functionality + json
  - client: includes auth functionality (inc. context, navbar, etc)
    - it also has .jsx extension + SERVICES + component for "loading", etc

  -- PROBLEM: if we use that, all the auth functionality will be given (students may not learn by implementing it)

  -- ALTERNATIVE:
    - generate as usual (ironlauncher --auth --json + Vite)
    - go through the units (students implement auth following students portal).
    - after that, we generate a project with "--fs" and we explain the little differences.

  -->
  
  - `mkdir project-management-fullstack` (IMPORTANT: create directory for both repos)
  - `cd project-management-fullstack`
  - `npx --yes ironlauncher@latest project-management-server --auth --json` 
    - (IMPORTANT: "--auth --json" )
  - `npm create vite@latest project-management-client -- --template react`

    <!-- 
  
    IMPORTANT:
    - initialize with ironlauncher --auth --json 
    - (so that we can speed up backend auth lecture) 
    
    -->




<!-- 

- React | Building the Rest API (time: 3.5h / and going a bit fast)
- React | Integrating the React App

  -> these 2 lessons, do them directly copying the content from students portal (make sure students understand all steps)
  -> (otherwise they take too much time)

-->


Common Pain point for many students:
- we will have 2 apps running (front & back)
  - Express API (Ironlauncher) - `npm run dev` (port 5xxx)
  - React App (Vite) - `npm run dev` (port 3xxx)
- naming:
  - frontend / client / react app
  - backend / server / express app

  <!-- @LT: show them (ie. run both apps on my computer) -->







<!-- 

@todo: 
- create CSS and provide it to students (it will help them understand the UI and the project better) 

-->



End of the day:
- Context API: ask students to do it as self guided (contains a lot of code, students may enjoy more doing by themselves)


