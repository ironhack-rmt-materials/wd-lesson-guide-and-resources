

# w2d5

Morning:

- Practice time:
  - improve game from previous day (some notes below)
  - students can also work on bonus labs OR time for questions (TA's)

Afternoon:
- Project 1 guidelines
  - see "w2d5 - f - Project 1 Guidelines (project 1 kick-off).md"
- Project planning session
  - students share what they have in mind and get feedback (main room / breakout rooms)
- Time to start planning / working on projects
- Game / Icebreakers



## Game Improvements


Game Improvements:

  - [ ] Display player in the center
  - [ ] Obstacles starting from random horizontal positions
  - [ ] fix: remove obstacles when they go outside board

  - [ ] (bonus) Refactor: create a Game class
      <!-- 
      
      @Luis: 
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
        - supermario: https://upload.wikimedia.org/wikipedia/en/a/a9/MarioNSMBUDeluxe.png

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
    - add images

