
# Node - Intro & Installation

<!--

- Part 1: follow students portal (highligted), untill 'Install and use packages from npm'
- Part 2: do the practice exercise with package 'cowsay' (below)


Status: draft

- @todo: 
  - improve this notes/planning +++
  - create slides

-->


# Intro

- JavaScript was created for browsers

- 2009 initial release of NodeJS
  - "Ryan Dahl" took the JS engine from Chrome (V8) and created some software that can run on servers
  - Result: we can now execute JS on servers

- Before Node, the only place where you could use JavaScript was a client-side environment. 
  - Thanks to Node, we can use JS in the backend side as well.


# Part 1 Summary

- What is NodeJS?
  - NodeJS = "Node"
  - "runtime environment" (environment with tools that allow to execute JavaScript)


- Node is "not":
  - Is not a programming language
  - is not a framework


- Advantages of Node:
  - Run JS on the server
  - Asynchronous functionality
  - Growing ecosystem (packages)


- Node Package Manager (npm)
  - what is a package manager



## Practice: init a project + install & use cowsay


- Explain what we want to achieve + Search for the package we want to use on NPM (https://www.npmjs.com/package/cowsay)


- Create directory

```
mkdir my-talking-cow
cd my-talking-cow
code .
```

- Initialize the project

```
$ npm init
```

- Open & explain package.json



- Install cowsay (show instructions for installation on npm but DO NOT INSTALL GLOBAL)

```
npm install cowsay
```

- Explain changes:
  - added dependencies to package.json
  - added package-lock.json (explain: dependencies of our dependencies)
  - added directory node_modules


- node_modules...
  - this folder has locally, on your machine, all the libraries/packages you defined in package.json
  - it shouldn’t be ever pushed to GitHub because:
    - it’s a huge folder and no need to be pushed, as well as,
    - anyone who clones your repository will be able to regenerate it with npm install based on the package.json.

  - In our projects, we will create a .gitignore file and add node_modules to it.


- Create index.js and use it
  - documentation: https://www.npmjs.com/package/ > Usage as a module
  - note: require() is a NodeJS built-in function (it's not part of the javascript standard)



## Extra practice (optional)

- Choose a package from this list of weird packages + read the docs, install and use it.
  https://github.com/sindresorhus/awesome-nodejs#weird



## Additional resources:

- The NPM guide I would have loved as a beginner
https://dev.to/spartakyste/the-npm-guide-i-would-have-loved-as-a-beginner-4i07


