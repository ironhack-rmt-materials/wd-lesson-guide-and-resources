
# Node - The concern on users' security

<!--
  
  Status: ready 


Time: 
  - Slides: 1h
  - Bcrypt Demo: 30min.

-->


## Links

- Slides: https://docs.google.com/presentation/d/1gNCZq7lZiph_Dzde34FuL6MI01c0ge1u3djxZMNWxPk/edit?usp=sharing


- Recording (dec. 2023): https://www.loom.com/share/99e0abae2c9346a3ba84d1e178c06b48?sid=e471b840-b8a6-44a1-9070-4f5a5f662518



## Bcrypt Demo


```
mkdir bcrypt-demo
cd bcrypt-demo
npm init --yes
npm install bcryptjs
touch app.js
code -r .
```


```js
const bcrypt = require('bcryptjs');
const saltRounds = 10;

const plainPassword1 = 'HelloWorld';
const salt = bcrypt.genSaltSync(saltRounds);
console.log(`Salt => ${salt}`);

const hash1 = bcrypt.hashSync(plainPassword1, salt);
console.log(`Hash 1: ${hash1}`);


const verifyPass1 = bcrypt.compareSync(plainPassword1, hash1);
```



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

Video: 7 Cryptography Concepts EVERY Developer Should Know (FireShip, 12min.)
https://www.youtube.com/watch?v=NuyzuNBFWxQ

Video Playlist: Basic Cryptography (Sunny Classroom)
https://www.youtube.com/playlist?list=PLSNNzog5eyduN6o4e6AKFHekbH5-37BdV

