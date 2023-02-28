
# OOP Game Codealong

<!--

Time estimation: 6-10h

-->





## Intro 

- Canvas vs DOM

  - Mario:
    - Canvas: https://tylerreichle.github.io/mario_js/
    - DOM: https://florian-rappl.de/html5/projects/SuperMario/

- Can I build "a cool game" just with dom manipulation?
  - Survivor Game (Jonny): https://jogopin.github.io/Survivor-game/


- Explain the kind of game that we want to build
  - examples (we will not have time for all): 
    - https://claradrojas.github.io/potato-run/index.html
    - https://zhosde.github.io/ninja-the-hacker/
    - https://ironborn-ironhack-march-2022.github.io/ironborn-oop-game/



- We will do:
  - OOP
  - DOM



- Goals:
  - Practice (dom, oop, js fundamentals...)
  - Learn coding good practices 
  - Learn git concepts 


- Warn students: 
  - some steps today may be a bit fast.


## IMPORTANT

1. Building a game together is a very interesting exercise but some students may have a tendency to then copy most of the code we produce (specially, if they find it difficult to start with their own code). To address that, 2 options:
  - Option1: 
    - build a "dog cross the road" type of game (and don't allow the option of this same game)
    - example: https://zenabos.github.io/dogshitty/
  - Option2: 
    - Be very very clear. If they build this kind of game they're expected to start from scratch and come up with they're own solution.
    - Also, show other patterns that they can use (OOP vs functions, etc)


2. Students find it difficult if we try to decouple logic from DOM manipulation. Instead, just build it together:
  - example1 (logic+dom): https://github.com/StrangerCodingThings-Ironhack-June-22/oop-game-codealong
  - example2 (aiming to detach logic & dom): https://github.com/Ironborn-Ironhack-March-2022/ironborn-oop-game



## Codealong

- Initial planning 
  - Share milestones + plan together how we can implement each milestone.
  - note: once we start coding we will probably follow different paths.


<!--

@Luis:
- first share with them the milestones / goals
- then do the planning together with students.


Milestone 1: user can move the player left/right

Milestone 2: obstacles appearing in the UI + obstacles move + we detect if there's a collision
  
  (note: for this milestone, it's ok if obstacles appear always at the same position)

Milestone 3: make the game more interesting & fix bugs
  - random position for obstacles
  - prevent player from going outside

-->



[ ] initial code
  - files
  - basic structure (board)
  - create repo + initial commit

[ ] Game class (note: we can start from Player and implement this one later)
  - start()

[ ] Player class
  - position (x, y)
  - moveLeft(), moveRight()
  - draw()

[ ] When game starts:
  - create Player and draw it on the board

[ ] Allow player movement

[ ] Obstacle class (create generic class and extend)

[ ] Create Obstacles
  - Start by creating only one obstacle
    - create new instance of the class Obstacle
    - move the obstacle (setInterval)
  - Then, change to create multiple obstacles

[ ] Detect collision
  - Collision detection
  - Gameover (ex. redirect)

  <!--

  @Luis: 

  gameover functionality (ex. redirect to gameover.html)

  -->

[ ] Remove obstacles when they're outside screen

[ ] Drop obstacles at random places

[ ] UX
  [ ] Add "how to play" page


## Improvements:

Fix:
- remove obstacles as they go outside board
- prevent player from moving outside

Functionality:
- obstacles starting from random horizontal positions
- shooting (recommended)
- drop different things (prizes, different types of obstacles...)
- count points
- improve game over
- leves
- multiple lives
- allow moving the player up and down
- settings (speed of the game, distance between obstacles)

UX:
- add "how to play" page
- add images (background, player, obstacles)
- sound


Good practices:
- Add README file

Code quality:
- reuse code with OOP inheritance 
- store settings as property of the Game class (ex. refreshRate)



## Final notes
- If they pick a similar game they will need to go further (implement other features etc)
- Some notes: https://stackblitz.com/edit/js-jvpqgw?file=index.js



## Codealong Examples

- MVP Example (can be a good example to follow):
  - https://github.com/ironicHackers-Ironhack-Sept-22/oop-game-codealong

- Codealong with OOP Inheritance + 1 single setInterval:
  - https://raw.githubusercontent.com/StrangerCodingThings-Ironhack-June-22/oop-game-codealong/main/js/main.js


## Extra Resources

- CSS Position property (refresh, before we write the css)
  - Learn CSS Position In 9 Minutes (9m): 
      <!-- @Luis: for the game, the first 6min. are enough (the other 3 min are useful: fixed, sticky) -->
    - https://www.youtube.com/watch?v=jx5jmI0UlXU
  - (Bonus) CSS Position Tutorial For Beginners (10min.): 
    - explains in further detail (more slowly)
    - https://www.youtube.com/watch?v=gD3G67oPg-w


