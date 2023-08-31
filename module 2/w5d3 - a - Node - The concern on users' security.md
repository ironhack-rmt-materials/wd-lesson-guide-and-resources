
# Node - The concern on users' security

<!--
  
  Status: ready 


Time: 
  - Slides: 1h
  - Bcrypt Demo: 30min.

-->


## Slides

https://docs.google.com/presentation/d/1gNCZq7lZiph_Dzde34FuL6MI01c0ge1u3djxZMNWxPk/edit?usp=sharing



## Bcrypt Demo

<!-- @Luis: do DEMO (not codealong) -->

- Follow students portal: "Demo"

- Specific things to explain:
  - bcrypt first characters (https://en.wikipedia.org/wiki/Bcrypt#Description)
    -- $2a: hash algorithm identifier
    -- $10: cost
    -- $xxxxx: salt
  - Bcrypt includes the salt in the hash (so we just need to store the hash in the db)

  - saltRound represents the cost factor (how much time is needed to calculate a single hash)
    -- bigger = more secure but it also takes more time and resources
    -- recommended: 10

- We can also use bcrypt asynchronously (eg. with promises)
  - example: https://github.com/ironhack-labs/code-lessons/blob/master/bcryptDemo/exampleWithPromises.js

- (extra challenge): practice bcrypt async with promises


## Extra Resources

A non-technical history of password storage:
https://analogist.net/post/a-non-technical-history-of-password-storage/

Online Bcrypt Hash Generator & Checker:
https://bcrypt-generator.com/ 

Password Strength: using a passphrase (an alternative for password requirements)
https://protonmail.com/blog/wp-content/uploads/2019/03/passwords_blog_protonmail.png


## Extra Resources 2 (videos with further topics)

Video: 7 Cryptography Concepts EVERY Developer Should Know (Fireship, 12min.)
https://www.youtube.com/watch?v=NuyzuNBFWxQ

Video Playlist: Basic Cryptography (Sunny Classroom)
https://www.youtube.com/playlist?list=PLSNNzog5eyduN6o4e6AKFHekbH5-37BdV