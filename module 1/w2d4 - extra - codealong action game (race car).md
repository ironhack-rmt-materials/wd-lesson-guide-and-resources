
# Codealong: action game (race car)

<!--

Time estimation: 6-10h

-->


## Intro 

- Canvas vs DOM

  - Mario:
    - Canvas: https://tylerreichle.github.io/mario_js/
    - DOM: https://florian-rappl.de/html5/projects/SuperMario/

- Goals:
  - Practice (dom, oop, js fundamentals...)
  - Learn coding good practices 
  - Learn git concepts 

- Explain the kind of game that we want to build
  - https://coding-ninjas-ironhack-sept-2021.github.io/Car-Race-Game/
  - example (we will not have time for all): https://zhosde.github.io/ninja-the-hacker/

- We will do:
  - DOM
  - OOP

- Plan together (how we can start, what kind of things we need)

## IMPORTANT

1. Building a game together is a very interesting exercise but some students may have a tendency to then copy most of the code we produce (specially, if they find it difficult to start with their own code). To address that, 2 options:
  - Option1: 
    - build a "dog cross the road" type of game (and don't allow the option of this same game)
    - example: https://zenabos.github.io/dogshitty/
  - Option2: 
    - Be very very clear. If they build this kind of game they're expected to start from scratch and come up with they're own solution.
    - Also, show other patterns that they can use (OOP vs functions, etc)
    - Some notes: https://stackblitz.com/edit/js-jvpqgw?file=index.js


2. Students find it difficult if we try to decouple logic from DOM manipulation. Instead, just build it together:
  - example (logic+dom): https://github.com/Ironmaidens-Ironhack-Jan-2022/oop-game-codealong/blob/main/js/game.js


## Codealong

Initial planning (once we start coding we will probably follow different paths):

[ ] initial code
  - files
  - basic structure (board)

[ ] Game class
  - start()

[ ] Player class
  - position (x, y)
  - moveLeft(), moveRight()
  - draw()

[ ] When game starts:
  - create Car and draw it on the board

[ ] Allow player movement

[ ] Obstacle class (create generic class and extend)

[ ] When game starts:
  - setInterval()
  - generate obstacles randomly
  - update obstacles positions (move down)

[ ] Detect collision

[ ] Remove obstacles when they're outside screen

[ ] Drop obstacles at random places


## Improvements:

Fix:
- remove obstacles as they go outside board
- prevent user from moving outside

Functionality:
- obstacles starting from random horizontal positions and/or random sizes for obstacles
- shooting (recommended)
- drop different things (prizes, different types of obstacles...)
- count points
- improve game over
- leves
- multiple lives
- allow moving the player up and down
- settings (speed of the game, distance between obstacles)

UX:
- add images (background, player, obstacles)
- sound

Code quality:
- apply OOP inheritance 
- detach logic & DOM manipulation



## Final notes
- If they pick a similar game they will need to go further (implement other features etc)

