

# Node - User registration

- @Luis: follow students portal (~~highlighted, july21~~)

- GOAL: allow users to create an account


## Step 0: User Model


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

    ```
    const bcryptjs = require('bcryptjs');
    const saltRounds = 10;
    ```


    ```
    bcryptjs
        .genSalt(saltRounds)
        .then(salt => bcryptjs.hash(password, salt))
        .then(hashedPassword => {
        console.log(`Password hash: ${hashedPassword}`);
        })
        .catch(error => next(error));
    ```

- Query DB

```
User.create(
    {
        // username: username
        username,
        email,
        passwordHash: hashedPassword
      }
)
```

- Once the account is created, redirect to a profile page
  - Create view (`views/users/user-profile.hbs`)
  - Create route (GET `/userProfile`)
  - Redirect (`res.redirect('/userProfile');`)


