

# LAB - React Tweets


How:
- Individual


<!-- 

Jan 2022: 
- some students running node v.17 we're having a problem running the problem.
- quick fix: https://stackoverflow.com/a/69713899/11298742

 -->





## EXPLAIN

- IMPORTANT: 
  - Students feel overwhelmed about creating one component for each small thing in the UI
  - Explain them that the goal of this lab is to practice components (this is why we over do it)

- Advice: force yourself to code & practice the syntax


## Iteration 2 | Pass the Tweet as a Prop

  - We're passing the a prop with the name `tweet`.
    `<Tweet tweet={ tweetsArray[0] }>`

  - In `<Tweet />` you can then read `props.tweet`
    - Important: `props.tweet` is an object
    - Understand the structure of this object (you can console.log or use react dev tools to see the props)
    - You can then access properties of this object.
      - Ex. `props.tweet.user`


## Iteration 9 | Render multiple Tweets

IMPORTANT: 
  - we still haven't seen how to iterate through arrays
  - students can just pass props statically:

    `<Tweet tweet={ tweetsArray[0] }>`
    `<Tweet tweet={ tweetsArray[1] }>`
    `<Tweet tweet={ tweetsArray[2] }>`

  - We will learn how to iterate tomorrow.



<!-- 
  
  Bonus homework: continue watching video 
  (details in today's "day planning" md file)

-->


<!-- 

- mandatory: LAB React Tweets
- (recommended) continue watching video 
- (bonus) do some katas from "HOF exercises"
- (bonus) do some components from lab "React Training" (can do steps 1-7)
- mandatory: take good rest (tomorrow is challenging)

 -->
