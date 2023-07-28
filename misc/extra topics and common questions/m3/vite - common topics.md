

# Vite


## Run on a specific port


- By default:

> Vite development defaults to the network port 3000. Or it tries to find an available port if it is already taken,


- Custom port through CLI: `npm run dev -- --port 3000`


## Environment variables

1. Create your environment variables in .env file
  - make sure variables start with "VITE_"  (ex. `VITE_API_URL`)

2. To use them: import.meta.env.xxx (ex. `import.meta.env.VITE_API_URL`)


Note: `.env` is not in .gitignore
(but `*.local` will be ignored; for example: ".env.local")


Source (stackoverflow): 
- https://stackoverflow.com/a/71406233/11298742
Documentation & more info: 
- https://vitejs.dev/guide/env-and-mode.html#env-files

