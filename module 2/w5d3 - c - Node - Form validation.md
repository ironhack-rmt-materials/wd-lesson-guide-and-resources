
# Node - Form validation


<!--

Status: draft


Intro Slides: 
https://docs.google.com/presentation/d/1JIdfc4TjXbdK6gtUTFrjgZ24gQyTSSHy1YJsa-6k2us/edit?usp=sharing


Notes:
  - All these 4 validation examples are implemented in ironlauncher (`ironlauncher --auth`)
  - Show and explain the code on there 
    - (as long as students understand it, we don't need to type all that code, for project2 they can use ironlauncher)

-->

## Client-Side vs. Server-Side validation

- follow slides


## 1. Make sure that users fill all the mandatory fields.

Intro:
- Add "required" to form fields
- Show how we can bypass client validation (eg. dev tools)


```javascript
  if (!username || !email || !password) {
    res.render('auth/signup', { errorMessage: 'All fields are mandatory. Please provide your username, email and password.' });
    return;
  }
```

```javascript
  {{#if errorMessage}}
    <p class="error">{{errorMessage}}</p>
  {{/if}}
```



## 2. Make sure users fill in data in the valid format.

See students portal (very briefly)


## 3. Make sure data in the database is clean - no duplicates please!

See students portal (very briefly)


## 4. Make sure users use strong passwords.

See students portal (very briefly)


