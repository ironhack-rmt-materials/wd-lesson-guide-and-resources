
# LAB - JS Chronometer - iteration 1


<!-- 

- iteration 1: not so difficult
- iterations 2,3,4: very challenging and take TIME

-->


# Iteration 1: logic
- we build the logic of the chronometer (tomorrow, we will do the UI)
- work only on "chronometer.js" and pass the tests.

Tricky things:
- method "start"
  - expects a callback (if it is a function, execute it)
  - for the interval, use an Arrow Function for `this` binding (it is stated in the instructions)

# Iteration 2: buttons & print time
- very challenging
- lengthy
- description is very very long

Sudents will need:
- read & modify classes on the DOM
  - interacting directly with className is difficult (eg. may need to parse a string to remove one class)
  - best option: user classList
    - elm.classList.remove("foo");
    - elm.classList.add()
    - elm.classList.toggle()


Tasks:
- update buttons (class and content)
- display time in the UI:
  - we need to call start() method and pass printTime() as a callback
  - implement functionality for printTime() (will call printMinutes() and printSeconds())
  
# Iteration 3: split
# Iteration 4: reset
# Iteration 5 (bonus): Milliseconds

