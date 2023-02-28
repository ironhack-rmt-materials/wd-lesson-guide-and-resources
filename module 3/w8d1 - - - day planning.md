
# w8d1


- Project 3: 
  - Show 2 examples of m3 projects.
    - first project with MVP requirements (auth, 3 models, CRUD)
    - second project more advanced.
  - They can start thinking what they want to build
  - Ask students to write TAs their preferences (pairs, teams etc)


- (optional) Refresh React concepts:
  - can be done in pairs (45m+15m) or all together (30m.)
  https://docs.google.com/document/d/1D20pulIvbXX70ljTCDvMj4wZyvCpM1ggGgZAZj-Nr7I/edit?usp=sharing





- Run Commands:

  <!--
  Update Jan 2023:
  
  - we could now use "npx ironlauncher@latest new-app --fs"

  - it will create 2 directories with server + client
  - server: includes auth functionality + json
  - client: includes auth functionality (inc. context, navbar, etc)
    - it also has .jsx extension + SERVICES + component for "loading", etc

  -- PROBLEM: if we use that, all the auth functionality will be given
     (students may not learn by implementing it)

  -- ALTERNATIVE:
    - generate as usual (ironlauncher --auth --json + CRA)
    - go through the units (students implement auth following students portal).
    - after that, we generate a project with "--fs" and we explain the little differences.


  -->

  
  - `mkdir project-management-fullstack` (IMPORTANT: create directory for both repos)
  - `cd project-management-fullstack`
  - `npx --yes ironlauncher@latest COHORTNAME-project-management-server --auth --json` 
    - (IMPORTANT: "--auth --json" )
    - (IMPORTANT: replace "COHORTNAME" )
  - `npx --yes create-react-app cohortName-project-management-client`


    <!-- 
  
    @Luis / IMPORTANT
    @Luis / IMPORTANT
    @Luis / IMPORTANT
    @Luis / IMPORTANT
    
    initialize with ironlauncher --auth --json 
    (so that we can speed up backend auth lecture) 
    
    -->




<!-- 

- React | Building the Rest API (time: 3.5h / and going a bit fast)
- React | Integrating the React App

  -> these 2 lessons, do them directly copying the content from students portal (make sure students understand all steps)
  -> (otherwise they take toooo much time)


  - Second lesson (" Integrating the React App")
    - will be better to ask students to do as self-guided (or provide a video)


-->



<!-- 

@todo: 
- create CSS and provide it to students (it will help them understand the UI and the project better) 

-->



End of the day:
- Context API: ask students to do it as self guided (contains a lot of code, students may enjoy more doing by themselves)




## IMPORTANT: ask students for preferences for project3


<!-- 

Students to do p3 individually:
- inform them in advance
- ask them to still submit their preferences 
- assess with the team (based on their preferences)

-->



Project 3 preferences:

```js
const myPreferences = {
      iWantToWorkwith: ["alice", "bob", "charly", "david", "elisabeth", "frank"], // 6 names, ordered by preference
      iPreferToAvoid: ["", ""] // max 3 names
}
```

- DEADLINE: xxx
- HOW: msg TA on slack
- We strongly recommend you doing project 3 in pairs (collaborating is essential as a web dev + you'll have more time to build a better project). If you really want to do it individually, mention that in your message to your TA

