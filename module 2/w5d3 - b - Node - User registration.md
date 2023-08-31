

# Node - User registration

<!-- 

- Sample repo:
https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/

-->



- GOAL: allow users to create an account

- NOTE:
  - today, we will see a lot of code
  - don't need to memorize all this (ironlauncher), just understand what we do


## Step 0: User Model

- email
- passwordHash

Sample: https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/main/models/User.model.js



## Step 1: display a form to create an account

- Create route (GET `/signup`) (inside `auth.routes.js`)
- Create a view (`auth/signup.hbs`)

  - (Extra) add "required" to form fields.

- We've also updated `layout.hbs` and `style.css`


## Step 2: process the form (create the account)

- Create route (POST `/signup`)
  - Inside this route, we will need to generate the hash (digest) and create the account in the DB

- Install bcryptjs (`npm install bcryptjs`)

- Generate hash

    ```js
    const bcryptjs = require('bcryptjs');
    const saltRounds = 10;
    ```


    ```js
    bcryptjs
        .genSalt(saltRounds)
        .then(salt => bcryptjs.hash(password, salt))
        .then(hash => {
        console.log(`Password hash: ${hash}`);
        })
        .catch(error => next(error));
    ```

- Query DB

  ```js
  User.create(
    {
      email,
      passwordHash: hash
    }
  )
  ```


  Example `POST /signup`:
  https://github.com/ByteWarriors-Ironhack-Feb-23/warriors-library-project/blob/b20b1d6cbaf74525fe4471b7286766abe2ad419e/routes/auth.routes.js#L17


## Step 3: once account is created, redirect to user profile page

- Once the account is created, redirect to a profile page
  - Create route (GET `/user-profile`)
  - Create view (`views/auth/user-profile.hbs`)
    - for now, just display a paragraph, (ex. "This is your profile page my friend!")
  - When account is created, Redirect (`res.redirect('/user-profile');`)


