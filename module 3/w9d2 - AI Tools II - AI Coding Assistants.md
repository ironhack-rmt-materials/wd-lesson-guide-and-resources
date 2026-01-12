

# AI tools II - AI Coding Assistants


## GitHub Copilot

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
    - example 1: how do i uninstall an npm package ? / provide a list with all endpoints in this api.
    - example 2: paste an error message (e.g. title is not defined)
    - show options:
        - ask
        - edit
        - agent
            - example: uninstall mongoose & paste the error "mongoose is not defined"
    - providing context
        - tip: if you need to add all files as context, use `#codebase`
    - `@workspace` (e.g.: how many models we have)
    - `@vscode` (e.g.: whats the shortcut to change the language mode for the current file)

- sparkles (e.g. commit message)



## (skip) Custom instructions file

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
    - e.g. `generate unit tests for all endpoints on the project model`

- And also to generate readme files (at least a first version).



## Other AI Coding Assistants

- Cursor
    - Cursor Tutorial for Beginners: https://www.youtube.com/watch?v=ocMOZpuAMw4

- Windsurf

- Google Antigravity



## (skip) Asychronous Background Coding Agents

Example using Copilot directly on Github (Addy Osmani):
- https://www.linkedin.com/posts/addyosmani_ai-programming-softwareengineering-activity-7389186792706506752-BWnR



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




## Resources

For latest updates and news on Github Copilot:
- https://www.youtube.com/@code


