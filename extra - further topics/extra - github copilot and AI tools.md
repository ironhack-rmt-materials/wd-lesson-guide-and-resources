

# Extra - GitHub Copilot



## Demo:

<!-- 
@LT: 
- for this demo, open a repo with an express application
- later on, can just create new files to demo this capabilities with React
-->


- url: https://github.com/features/copilot/plans 

- settings
    - eg: enable/disable
    - choosing model

- code completions:
    - `function findLongestStringInArray(){}`
    - `const words = []`

- code suggestions from comments
    - example 1:
        - `// function to find the average in an array of numbers`
    - example 2:
        - `// GET /drinks`
    - example 3:
        - create file middleware/isOwner.js 
        - `// middleware function to verify if the user is the owner of the resource`

- inline chat and speech-to-text
    - note: now it's available in the copilot menu (at the top)
    - example 1: create a function that takes two arrays and returns true if they have exactly the same values
    - example 2: make this function generic, so that it works with any nested levels (ie. arrays of any depth).

- chat in sidebar:
    - choosing model (included vs. premium)
    - passing/defining context
        - instructions file (see below)
    - example 1: how do i uninstall an npm package ?
    - example 2: paste an error message (e.g. title is not defined)
    - show options:
        - ask
        - edit
        - agent
            - example: uninstall mongoose & paste the error "mongoose is not defined"
    - `@workspace` (e.g.: how many models we have)
    - `@vscode` (e.g.: whats the shortcut to change the language mode for the current file)

- sparkles (e.g. commit message)



## Custom instructions file

> Instruction files enable you to specify custom instructions in Markdown files. 
> You can use these files to define your coding practices, preferred technologies, and project requirements.

- `.github/copilot-instructions.md`: a single instruction file that contains all the instructions for your workspace. These instructions are automatically included in every chat request.

- example: 

    ```md
    General Guidelines:
    - Use modern JavaScript/TypeScript (ES6+).
    - Follow project coding standards and existing patterns.
    - For React projects, prefer functional components and hooks.

    Tech stack & preferred Libraries:
    - React
    - Next.js
    - Tailwind CSS
    - Axios (for HTTP requests)

    File Structure:
    - Use `components/` for reusable UI components.
    - Use `pages/` for route-level components (Next.js).
    - Use `utils/` for utility functions and API logic.

    Other notes:
    - For promises, use async/await

    ```

- more info: https://code.visualstudio.com/docs/copilot/copilot-customization


## Tips:

- Copilot can be really good at doing things with existing libraries and apis (especially if they're popular & not very recent)
    - e.g.: `// get most popular artists from spotify api`

- It can also be useful to generate unit tests
    - e.g. `unit tests for a function that will receive a string and verify if it's a valid email address`



## Other AI Editors

- cursor
    - Cursor Tutorial for Beginners: https://www.youtube.com/watch?v=ocMOZpuAMw4

- windsurf

- Cline (AI coding agent)
    - https://github.com/cline/cline
    - examples:
        - Generate, edit and refactor files
        - Run and interact with your terminal
        - Automate browser actions for debugging or testing


## Other AI tools

- UI generators: v0.dev (react, tailwind)

- Low-code development & prototyping: 
    - bolt.new
    - lovable.dev
    - replit.com
    - firebase.studio (tried it in april 25, a few days after release, and results were quite poor)
    - github.com/spark
        - https://github.blog/changelog/2025-07-23-github-spark-in-public-preview-for-copilot-pro-subscribers

- Gemini canvas: https://www.linkedin.com/posts/addyosmani_programming-softwareengineering-ai-activity-7308542354821394432-AdnZ


Examples:
- create an Instant Resume Analyzer

- For an app that will allow users to practice their language skills by having a realtime voice conversations with an AI, create the private area for logged in users (users need to be able to start a new conversation, see how many minutes they have remaining, see some stats, logout, etc).

- create the homepage for a furniture company that offers beautiful pieces of furniture and shipping everywhere in Germany

- create a REST API with Express and PostgreSQL. API should implement auth functionality with jwt, CRUD on projects and CR on tasks.

- Create a react app to generate random pairs with students. The app will let you create a cohort & add a list of students for that cohort (by entering all the names in comma separated format). Once you have created a cohort, you can generate random pairs (if there's an odd number of students, it will generate a group of 3). If you like the pairs generated, you can click a button to confirm. One you confirm, those pairs will be added to a "pairs history". The user can visit the pairs history to see a table with all the students that have already been matched together. Also, when you create new random pairs, the app will avoid pairing students that have already worked together.

Use cases:
- Quick prototypes +++
- Brainstorming (if you don't have clear specs, it may be great to give you some interesting ideas) +
- It can also be useful to create basic apps or specific components (specially when the problem is not too complex and the instructions are very well defined)


## Agent mode + MCP Servers

VS Code: Agent Mode + MCP Servers + BYOK
https://www.youtube.com/watch?v=dutyOc_cAEU


Demo: 
- Firebase MCP on VS Code


## Limitations

AI tools for Greenfield projects vs. commercial large codebases:
- https://www.linkedin.com/posts/gergelyorosz_something-i-hear-very-little-talk-about-activity-7333488796627349505-QZnw




## Warnings ⚠️ 

- As you can see, to be a prompt engineer, one "must" know how to code.
- Using AI to find quick solutions vs. learning
    - If you're learning a new technology, make sure you type things
    - "You will not learn a language by using Google Translator"

- Will AI replace developers? How to use AI to help you land a job?
    - https://chatgpt.com/share/6824e153-86ec-8003-a44f-33c5d9197b60


- (meme) When I try out vibe coding with AI:
    - https://thecodinglove.com/when-i-try-out-vibe-coding-with-ai



## Resources

Is AI really making software engineers 10x more productive? (Addy Osmani)
- Linkedin post: https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7363819659109793793-6q6_
- Full article: https://addyo.substack.com/p/the-reality-of-ai-assisted-software




## Videos

Old videos:
- Get to know GitHub Copilot in VS Code and be productive IMMEDIATELY (VS Code, 5min.)
    - https://www.youtube.com/watch?v=jXp5D5ZnxGM&t=2s
- GitHub Copilot in VSCode: Top 10 Features Explained (Max on Tech, 9min.)
    - https://www.youtube.com/watch?v=2nPoiUJpDaU


For latest updates and news,
- https://www.youtube.com/@code


