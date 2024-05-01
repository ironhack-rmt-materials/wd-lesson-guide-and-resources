
# OOP Game Codealong

<!--


Demo (type of game that we'll be building):
https://ironborn-ironhack-march-2022.github.io/ironborn-oop-game/

-->




## Intro 

- What is Canvas. 
- Examples:
  - https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes
  - https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_animations#result


- Canvas vs DOM

  - Mario:
    - Canvas: https://tylerreichle.github.io/mario_js/
    - DOM: https://mario5.florian-rappl.de/

- Can I build "a cool game" just with dom manipulation?
  - Survivor Game (Jonny): https://jogopin.github.io/Survivor-game/


- Explain the kind of game that we want to build
  - examples (we will not have time for all): 
    - https://claradrojas.github.io/potato-run/index.html
    - https://ironborn-ironhack-march-2022.github.io/ironborn-oop-game/



- We will do:
  - OOP
  - DOM



- Goals:
  - Practice (js fundamentals + oop)
  - Learn coding good practices 
  - Learn git concepts 


- How:
  - Initial planning
  - Project setup
  - Codealong


- @students: 
  - Some steps today may be fast.
  - Most students find it difficult (code is complex). Stay focused.





## Codealong

- Initial planning 
  - Share milestones + plan together how we can implement each milestone.
  - note: once we start coding we will probably follow different paths.


<!--

@LT:
- first share with them the milestones / goals
- then do the planning together with students.


note: we will use OOP + DOM.


Milestone 1: user can move the player left/right


Milestone 2: obstacles appearing in the UI + obstacles move
  
- note: for this milestone, it's ok if obstacles appear always at the same position

Milestone 3: detect if there's a collision

Milestone 4: make the game more interesting & fix bugs
  - random position for obstacles
  - prevent player from going outside

-->



[ ] (demo) initial setup [30min]
  
  <!-- 
  
  IMPORTANT: 
  
  - to speed up, tell students to just follow me for this first step 
  - (later, they can clone)

  -->
  
  - create files (html, css, js)
  - basic structure (board)
  - create repo + initial commit
  - upload repo to github

  <!-- also, share live session -->

[ ] Upload to Github + ask students to fork + clone

  - fork + clone + open in VS Code + run with Live Server
  - open with Live Server

[ ] Introduce Pomodoro technique
  - https://pomofocus.io/

[ ] (SKIP FOR NOW) Game class
  - note: we can start from Player and implement this one later.
  - start()

[ ] Player class
  - position (x, y)
  - moveLeft(), moveRight()
  - draw() [skip]
  <!-- consider: add event listeners before drawing ? -->

[ ] When game starts:
  - create Player and draw it on the board

[ ] Allow player movement

[ ] Obstacle class (create generic class and extend)

[ ] Create Obstacles
  - step1: start by creating `only one obstacle`
    - create new instance of the class Obstacle
    - move the obstacle (setInterval)
  - step2: then, change to create `multiple obstacles`

  <!--

  @LT: 
  - to explain these concepts, sometimes it helps to open a new file & create a simplified version of our code.
  - ex. "Enemy" class + "sayHello()" method

  -->


[ ] Detect collision
  - Collision detection
  - some notes: "collision detection - common errors.md"

[ ] Gameover (ex. redirect)

  <!--

  gameover functionality
  - redirect to gameover.html
  - include link to play again


  Recommendation:
  - index.html (instructions)
  - game.html (game)
  - gameover.html


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
- score
- improve game over page
- display score in gameover page (can be implemented using localstorage)
- levels
- multiple lives
- allow moving the player up and down
- allow diagonal movement (example: https://codepen.io/luisjunco/pen/yLZaoKN)
- settings (speed of the game, distance between obstacles)

UX:
- add "how to play" page
- add images (background, player, obstacles)
- sound


Good practices:
- Add README file

Code quality:
- create a Game class
- store settings as property of the Game class (ex. refreshRate)
- reuse code with OOP inheritance 




## Final notes
- If they pick a similar game:
  - start from scratch 
  - go further (implement other features etc)
- Show other patterns that they can use (OOP vs functions, etc)
- Some notes: https://stackblitz.com/edit/js-jvpqgw?file=index.js




## Codealong Examples

- MVP Example (can be a good example to follow):
  - https://github.com/ironicHackers-Ironhack-Sept-22/oop-game-codealong

- Codealong with OOP Inheritance + 1 single setInterval:
  - https://raw.githubusercontent.com/StrangerCodingThings-Ironhack-June-22/oop-game-codealong/main/js/main.js



<!--
Pong game codealong (dom + functions) (Jorge):

- https://codepen.io/jorgeberrizbeitia/pen/QWVQeXq

- https://gist.github.com/jorgeberrizbeitia/30a1a846ca837090423e921bf9d173ac

-->


## (skip) requestAnimationFrame()

- example commit: 
https://github.com/ironhack-tech-trash-july2023/oop-game-codealong/commit/fcb32f91872b7f9aa5fc066061c80314d64eb6fd



## (Extra) Refresh CSS Position


  <!-- remember to fork -->
- Initial code: https://codepen.io/luisjunco/pen/GRYYdjX
  <!-- remember to fork -->


- CSS Position property (refresh, before we write the css)
  - Learn CSS Position In 9 Minutes (9m): 
      <!-- @LT: for the game, the first 6min. are enough (the other 3 min are useful: fixed, sticky) -->
    - https://www.youtube.com/watch?v=jx5jmI0UlXU
  - (Bonus) CSS Position Tutorial For Beginners (10min.): 
    - explains in further detail (more slowly)
    - https://www.youtube.com/watch?v=gD3G67oPg-w



## (Extra) Axis

Axis (x, y) without legend: 
- https://nova-live.imgix.net//migration-HowtoUseChartsandGraphsEffectivelyIMGB2.jpg?q=60&fm=webp&w=700&h=700


Axis (with legend): 
- https://www.freemathhelp.com/images/lessons/xy1.png

Axis with legend (inc. negative values):
- https://study.com/cimages/multimages/16/axisgraph3795074999033209767.png


## (Extra) Collision detection

- Video: Rectangular Collision Detection with JavaScript (11min.)
  - https://www.youtube.com/watch?v=_MyPLZSGS3s&t=469s
  - Note: uses canvas + sets the origin in the top-left corner (in class, we use bottom left as a reference)
