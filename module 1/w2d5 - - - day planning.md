

# w2d5



## Day Planning
- OOP Game: demo  [5-6h]
- Project 1 kick-off [1h]
- Project planning session / feedback [1h]

 <!-- IMPORTANT: mark lab "DOM | Race Car Game" as bonus -->


# (skip) Refresh
  - value vs. reference
  - implications 
      ex.: comparing 2 arrays with the same contents
      ex.: making a copy of an array
  - how to copy arrays / objects
  - Timeouts & intervals
    - setTimeout(), setInterval()




## Game Improvements

Game Improvements:

  - [ ] Display player in the center
  - [ ] Obstacles starting from random horizontal positions
  - [ ] fix: remove obstacles when they go outside board
        - opt1: hide with overflow hidden
        - opt2: remove (from array + dom element) 

  - [ ] (bonus) Refactor: create a Game class
      <!-- 
      
      - alternative 1: record video (self-guided bonus)
      - alternative 2: give the final code + ask them to read & understand the code
      
      -->

  - [ ] README.md file

  - [ ] Discuss:
        - images
          - ratios
          - quality & size
          - license
          - name
        - use relative paths
        - timers (avoid nesting)
        - further improvements
        - if students build this type of game


  - Images (ex. background)
        - Note: can do in a break + push
  - Notes on images (ratio)
        - Super Mario: https://upload.wikimedia.org/wikipedia/en/a/a9/MarioNSMBUDeluxe.png

        ```js
        this.width = 5;
        this.height = this.width * 7;
        ```
  - (extra) Notes on OOP inheritance
       - example: https://stackblitz.com/edit/js-empgse?file=index.js
       - example of oop game applying inheritance: https://stackblitz.com/edit/js-po1rmg?file=index.js


Bonus:
    - prevent player from moving outside
    - allow moving the player up and down
    - one interval only (hint: you'll need to keep track of time -ex. a new property this.time)
    - implement/think: shooting

