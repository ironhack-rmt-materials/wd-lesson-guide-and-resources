
# TS - ExpressJS with TypeScript

<!-- 

status: draft


Template (Express + TypeScript template):
- https://github.com/ironhack-sept2024-devstructors/m4-express-ts-template



Example repo (event management): 
- https://github.com/luisjunco/m4-event-management-backend
- stack: express + typescript + prisma
- notes:
    - for promises, it uses async await
    - for codealong, simplify the schema (just "title", "description", "price")

-->



## Prisma methods - autocompletion

IMPORTANT: when we generate an instance of Prisma client, make sure to use ESM (so that we get TypeScript autocompletion):



```ts

// /src/db/index.ts

import { PrismaClient } from '@prisma/client';  // notice, we'reusing import

const prisma = new PrismaClient();

export default prisma; // notice, we're using export

```



Then, in our routes file, we also import it as ESM:


```ts

// event.routes.ts

import prisma from '../db/index'; // // notice, we'reusing import

```