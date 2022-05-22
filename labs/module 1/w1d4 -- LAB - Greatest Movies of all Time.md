# LAB | Greatest Movies of all Time

[REPO](https://github.com/ironhack-labs/lab-javascript-greatest-movies)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/151ab9fb30e923541247aa31b8e15a55)

### REMIND

- Fork
- Clone
- git add, commit, push  
  <br>
- PR
- submit LAB on SP -> share PR!! Not github link !  
  <br>
- npm install
- npm run test:watch

### Guidelines for LAB

- 250movies in data
    - test will insert it automatically
    - data is already imported!! Do not need to do anything extra.
- if you test on code in codepen -> copy array with only couple of movies/objects
- two tabs open in vsCode (movies.js + data.js)

## TIPS

- these methods can and will be complex in the beginning. Just go back to syntax and try to implement it. 
- no for loops!!
- some methods MUTATE original array - in that case you want to make a copy before you manipulate it

### ITERATIONS

6 iterations + bonuses
- it 1. MAP

- it 2. FILTER
    - look at a data you have:
    - director -> string
    - genre -> array

- it 3. REDUCE
    - Follow syntax/refer to student portal
    - read errors! Might need to check if this property exists, or if array is not empty etc
    - when working with object, you have to have initial value. 

- it 4. FILTER + REDUCE
    - genre is an array

- it 5. SORT
    - DO NOT MUTATE ORIGINAL ARRAY (test will say that)
    - copy array (clone)
    - [HOW TO CLONE ARRAY IN JS](https://www.freecodecamp.org/news/how-to-clone-an-array-in-javascript-1d3183468f6a/)
    - pay attention when sorting: case sensitive
    - sort sorts by alphabet

- it 6. Return ONLY first 20 titles.
