# Project 1 - How do I Start?

## TIPS

Plan what you want to do on the project and how to do it:

- Use some kind of task manager (ex.: Trello, Miro or others)

- Break the tasks in smaller tasks (ex.: "Build a Game" => "Create the      board", "Create a start method", "Create a player")

- Split tasks in essentials for delivery (MVP) and extras (features that you would like to implement but aren't essential)

### HOW YOU CAN START

#### Local repo

- On the terminal you could:

  - Create the folder for the project

  - Move into the folder

  - Open the folder on the VSCode

```
  $ mkdir <name-of-your-project> 
  $ cd <name-of-your-project>
  $ code .
```

- On a terminal (Could be the one on VSCode or the normal terminal if your prefer, make sure you're in the right folder!!!):

  - Initialize git

  - Create folder structure

  - Create the files

  - Add the folders/files to be tracked by git

  - Commit the modifications

``` 
  $ git init
  $ mkdir scripts styles
  $ touch index.html scripts/script.js styles/style.css README.md
  $ git add . // or git add <specific-files>
  $ git commit -m 'create project structure'
```

#### Remote repo

- Create a repo on GitHub, without README.md, .gitignore or licence

- Let the repository public

- GitHub has a step-by-step connect your local repo to the remote repo

```
  $ git remote add origin <url-from-github-repo>.git
  $ git branch -M main
  $ git push origin main
```

#### DEPLOY (just a help to speed process on Wednesday)

Have a `index.html` on the root of your project as the main file that will get all the updates and css stylesheets and js files (or the first page to access your `game.html` after)

### DEPLOY

- Open your GitHub Remote Repo  Example: <https://github.com/F-Mantovani/Project1-Mysterium>

- Go to `Settings`

- Find `pages` on the left and click it

- Keep Deploy from a Branch

- Select `main`  // or `master` if you didn't changed it

- Use the `/(root)`

- Click on `save`

### AFTER Deployment

- Grab the link of the running game (not repo's link) => Paste on Deliverables/Deployed project Example: <https://f-mantovani.github.io/Project1-Mysterium/>
- Grab the link for the GitHub project => Paste on Deliverables/GitHub repo Example: <https://github.com/F-Mantovani/Project1-Mysterium>

#### COMMON BUGS FIX

- Images or CSS changes not displaying after commit (Try one below - It can be a cache problem):
  - Refresh the page
  - Hold Click or Ctrl + Click on refresh button
  - Put a question mark at the end of url and add something there so the browser is forced download assets again <https://f-mantovani.github.io/Project1-Mysterium/?thisisaforcerefresh>
  - Remove the cache data from the browser

#### Adding images

- Make sure to use relative path for images. Example: background-image: url("../Mysterium/images/you-won.png");

##### Resources not loading

- Make sure to use relative paths
- Check console of the deployed version to see if the contents have been loaded

##### Relative paths on JS:

The JS is being loaded on the HTML, so the relative path should be from the `.html` and not the `.js`

[Gist](https://gist.github.com/TA-Remote/95001062235363e2fc8441825c7f0948)
