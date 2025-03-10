
# w8d2


## Day planning:

- Questions from yesterday

- running 2 apps in development (eg. 2 vs code windows + their own terminals)

- ironlauncher --auth --json [1.5h]
  - topics:
    - create the app with ironlauncher
    - launch (`npm run dev`)
    - see `package.json` (dependencies + scripts)
    - quick overview of initial code (models + routes)
    - understand the flow of the application
    - see the initial code for auth + middleware for auth
    - test with postman
  - more notes in `Express - Ironlauncher.md`

- environment variables [20m]
  - see notes below

- Project kickoff
  - Requirements [30m]
  - Activity [30m]
  - Recommendations [30m]

- Project planning (in pairs) [90m]
- Project planning session & feedback on models (in main room / squads)





## Environment variables


Backend / Express:

  1. How to add environment variables in the Backend / Express:
    - For development, we use a `.env` file
    - For production, we will add them on Render.com

  2. How to use them in the code (in express): `process.env.XXXX` (ex. "process.env.ORIGIN")



Frontend / Vite:

  1. How to add environment variables in the Frontend / Vite:
    - For development, we use a `.env` file (important: make sure variables start with `VITE_` for example, "VITE_API_URL")
    - For production, we will add them on Netlify.

  2. How to use them in the code (in Vite): `import.meta.env.xxx` (ex. "import.meta.env.VITE_API_URL")

  Note: `.env` is not in .gitignore
  (but `*.local` will be ignored; for example: ".env.local")



## Project3 kick-off 

- Students portal: "Project #3 Guidelines: MERN Web Application"

- Slides Project3 kick-off:
  - https://docs.google.com/presentation/d/1T4AixtKcqF5XXUSG-G8-v7PQG-f1OOGIT-8f_vPtA5c/edit?usp=sharing

