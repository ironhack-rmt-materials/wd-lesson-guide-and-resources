

# Deployment m1


## Recording

https://www.loom.com/share/a183261549334d4aad2c916c54c266e0?sid=434fba10-37d3-49a9-9701-fcd67ae55b61



Known errors in the recording:

- (minor): 14:45 correct syntax should be `elm.style.backgroundImage = "url('./images/background.jpg')";`




## Summary (Common Pain Points + How to Debug)


Common Pain Points:

1. You need an `index.html` file (your entry point)
   - index.html  --> gameover.html
   - index.html  --> play.html --> gameover.html

2. Make sure to use `RELATIVE PATHS`
   ./
   ../

   Note: in case you do that using dom manipulation, the link needs to be relative to your .html file (not to the .js).

3. If you don't see your changes, it may be because of the `cache`.
   - Check that your code is actually on Github.
   - If you need to invalidate the cache, these are some options:
     - Ctrl + F5 (hard reload)
     - Ctrl + hold click on the refresh button
     - Add "?pizza1" at the end of the URL
     - Clear the cache in your browser

4. (less common) Git is "not" case-sensitive
  - Example: if you have renamed a file "MyFile.png" to "myfile.png", git will have missed that change.
  - Possible solution: https://stackoverflow.com/a/40307511/11298742



How to debug:
  - Check if there's any error in the console.
  - Resources not loaded ? Check that the path is correct.
  - Check if your code on GitHub is the same one that in localhost
    - ex. forgot to push, error when you push, etc.




## Recording Script

- Goal: publish the applications we build in module 1.

- Show my game in localhost
  - If I was to share a link with a friend/users, they woudn't be able to play (local environment)

- Intro basic concepts (follow slides)
  - slides: https://docs.google.com/presentation/d/1teN_ZRHQBi60T0wS7bfDLZWu9Mi23iYTrSgq6WSSolk/edit?usp=sharing
  - what is deployment
  - dev vs. production environments
  - other environments

- m1 deployment: 
  - github pages
  - relatively simple (m2 and m3, more complex patterns, databases etc)

- Demo: how to deploy on Github Pages
  - github repo - settings - pages
  - git branches: https://the-turing-way.netlify.app/_images/sub-branch.png 
  - note: UI can change at any point.




Common pain points & bug fixing:

- `index.html` will be the entry point (at the top level of the source folder)
  - wrong example:
    - /mygame.html (need to rename + commit + push)
  - possible patterns:
    - example 1: index.html - gameover.html
    - example 2: index.html - game.html - gameover.html


- Relative paths

  - 1. Explain: 
    - "Absolute path": specifies the complete location of a file or directory, starting from the root directory, 
    - "Relative path": describes the location relative to the current location.

  - 2. Show example (ex. in my filesystem)

  - 3. project 1: use relative paths

  - 4. Examples:
    - JS and CSS from html file: `./`
      - show demo (fix + commit + push)
    - urls in CSS: `../`



- add image
  - start with absolute path (will work on localhost but fail on GH pages)
    - `background-image: url("/images/background.jpg");`
  - show how commit & push will be reflected live
  - see how it fails on production
  - fix using relative path + explain cache


- exception: resources loaded from your JS code with dom manipulation (must be relative to the html file)

- Cache:
  - a mechanism to store data that is frequently used.
  - diagram (browser cache): https://wp-rocket.me/wp-content/uploads/2022/12/Illustration-of-how-client-side-caching-works.png
  - goal: improve performance

- Other common pain points:
  - case-sensitive on github
    - recommendation: lower-kebab-case (but if you haven't follow, you may want to avoid touching it)


- How to debug:
  - Check if there's any error in the console.
  - Resources not loaded ? Check that the path is correct.
  - Check if your code on GitHub is the same one that in localhost
    - ex. forgot to push, error when you push, etc.


- Next steps:
  
  - Link to production: now you have a link public on the internet (so that anyone can test your game)

  <!-- Submit URLs in the students portal -->

  - Continuous deployment
    - You can continue working on your game as usual
    - Everytime you push code to the main branch, it will be deployed.

  - (skip) intro git branches (see `extra - git branches.md`)
    - note: do just a quick demo on a visual tool (it can be a bit too early to introduce branches)


<!-- IMPORTANT -->
<!-- IMPORTANT -->
<!-- IMPORTANT -->
- Ask students to submit urls (repo + github pages) on students portal
  - (Set DEADLINE)
<!-- IMPORTANT -->
<!-- IMPORTANT -->
<!-- IMPORTANT -->

