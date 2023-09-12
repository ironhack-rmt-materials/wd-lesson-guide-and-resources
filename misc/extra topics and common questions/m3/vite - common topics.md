

# Vite


## Run on a specific port


- Default:

  > Vite development defaults to the network port 3000. Or it tries to find an available port if it is already taken.


- Custom port through CLI: 
  - `npm run dev -- --port 3000`


- Custom port in config file:

  ```js
  // vite.config.js
  import { defineConfig } from 'vite'

  export default defineConfig({
    server: {
      port: 8000,
    },
  })
  ```


- Custom port in config file + environment variable:

  - add environment variable to .env (ex. `VITE_PORT=8002`)

  ```js
  import {defineConfig, loadEnv} from "vite";
  import react from "@vitejs/plugin-react";

  // https://vitejs.dev/config/
  export default defineConfig(({mode}) => {
    const env = loadEnv(mode, process.cwd());

    return {
      plugins: [react()],
      server: {
        port: env.VITE_PORT,
      },
    };
  });
  ```



## Environment variables

1. Create your environment variables in .env file
  - make sure variables start with `VITE_`  (ex. "VITE_API_URL")

2. To use them: `import.meta.env.xxx` (ex. "import.meta.env.VITE_API_URL")


Note: `.env` is not in .gitignore
(but `*.local` will be ignored; for example: ".env.local")


Source (stackoverflow): 
- https://stackoverflow.com/a/71406233/11298742
Documentation & more info: 
- https://vitejs.dev/guide/env-and-mode.html#env-files

