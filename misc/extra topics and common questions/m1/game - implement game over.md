
# How can I implement "Game Over" functionality ?





## Option 1 (easiest): redirect to another file
- functionality of the game is in one file (e.g. index.html). This is where the user can play.
- when user dies: redirect to another html file (e.g. gameover.html)
  - how to redirect in javascript: do some research ;)
  - note: in gameover.html, you probably want a link to play again (e.g. link to index.html)




## Option 2: redirect with query string
- Similar to the previous one but, when you redirect, you use the `query string` to send information to the second page.
- For example, redirecting to `gameover.html?points=24`
- Then, in the second page, you'd need to:
  - Read the information from the query string.
    - Research: "js read info from query string"
    - Example: https://stackoverflow.com/a/9870540/11298742
  - Use that information (e.g. use dom manipulation to display the amount of points) 



## Option 3: all the logic in the same file + DOM manipulation
- all the logic for the game in the same file.
- if we detect gameover, we will do all the steps needed. Depending on the game, you will probably need:
  - Some things for the logic (e.g. update variables or properties, cancel intervals...)
  - Some things for the UI (DOM manipulation)

- Note: this option is very flexible (you can do a lot of cool things) but can be more complex, depending on what you want to do.


