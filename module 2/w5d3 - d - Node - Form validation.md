
# Node - Form validation


<!--

Status: draft

@Luis: 
  - follow students portal (~~highlighted, july21~~)
  - I also have some slides

Note: 
  - All these 4 validation examples are implemented in ironlauncher (`ironlauncher --auth`)

-->

## Client-Side vs. Server-Side validation

- follow slides


## 1. Make sure that users fill all the mandatory fields.

Intro:
- Add "required" to form fields
- Show how we can bypass client validation (eg. dev tools)


```
  if (!username || !email || !password) {
    res.render('auth/signup', { errorMessage: 'All fields are mandatory. Please provide your username, email and password.' });
    return;
  }
```

```
  {{#if errorMessage}}
    <p class="error">{{errorMessage}}</p>
  {{/if}}
```



## 2. Make sure users fill in data in the valid format.

(can skip this one)


## 3. Make sure data in the database is clean - no duplicates please!

See students portal


## 4. Make sure users use strong passwords.

See students portal
