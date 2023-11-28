
# Node - Introduction

<!--

update - m2-m3 swap:

- part 1: very quick intro to node.js (2min.)
- part 2: npm - already done in m2 (skip)

-->




# Intro

- JavaScript was created in the 90s
- It was created for browsers
- For many years, the only place where you could use JavaScript was a client-side environment.


- 2009 release of NodeJS
  - "Ryan Dahl" took the JS engine from Chrome (V8) and created some software that can run JavaScript on servers
  - Result: we can now execute JS on servers
  - Thanks to Node, we can use JS in the backend side as well.



# Part 1 Summary

- What is NodeJS?
  - NodeJS = "Node"


- Node is "not":
  - Is not a programming language
  - is not a framework


- Advantages of Node:
  - Asynchronous functionality
  - Run JS on the server (for us, that's specially useful, we don't need to learn a new language)
  - Growing ecosystem (packages)


- Node Package Manager (npm)
  - what is a package manager
  - Example of a package: convert Celsius to Farenheit



## Practice: init a project + install & use cowsay


- Explain what we want to achieve + Search for the package we want to use on NPM (https://www.npmjs.com/package/cowsay)


- Navigate to ironhack directory + create  `module2` directory
  ```
    mkdir module2
    cd module2
  ```

- Create directory

  ```
    mkdir npm-demo
    cd npm-demo
  ```

- Initialize the project

  ```
    $ npm init
  ```

- Open with VS code
  ```
    $ code .
  ```


- Explain `package.json`



- Install cowsay (show instructions for installation on npm but DO NOT INSTALL GLOBAL)

  ```
    npm install cowsay
  ```

- Explain changes:
  - `npm install` vs `npm install -g`
  - added dependencies to package.json
    - semantic versioning
  - added package-lock.json (explain: dependencies of our dependencies)
  - added directory node_modules


- node_modules...
  - this folder has locally, on your machine, all the libraries/packages you defined in package.json
  - it shouldn’t be ever pushed to GitHub (it’s huge)
    - heaviest objects in the universe: https://preview.redd.it/tfugj4n3l6ez.png?auto=webp&s=b8163176d8482d5e78ac631e16b7973a52e3b188
    - anyone who clones your repository will be able to regenerate it with npm install based on the package.json.

  - In our projects, we will create a .gitignore file and add node_modules to it.


- Create `index.js` and use it
  - documentation: https://www.npmjs.com/package/cowsay > Usage as a module
  - note: require() is a NodeJS built-in function (it's not part of the javascript standard)



Tip: Debugging vs. reading documentation:
![debugging vs reading](./images/debugging%20vs%20reading%20documentation.jpg)




## Extra practice (optional)

- Choose a package from this list of weird packages + read the docs, install and use it.
  https://github.com/sindresorhus/awesome-nodejs#weird



## Additional resources:

- (Extra) The NPM guide I would have loved as a beginner
https://dev.to/spartakyste/the-npm-guide-i-would-have-loved-as-a-beginner-4i07


