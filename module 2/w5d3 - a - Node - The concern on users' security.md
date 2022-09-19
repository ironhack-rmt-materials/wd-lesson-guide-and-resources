
# Node - The concern on users' security

<!--
  
  Status: ready (just need to link slides)


Time: 
  - Slides: 1h15min (try to make it in 1h)
  - Bcrypt Demo: 40min.

-->


## Slides

https://docs.google.com/presentation/d/1gNCZq7lZiph_Dzde34FuL6MI01c0ge1u3djxZMNWxPk/edit?usp=sharing



## Bcrypt Demo

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

