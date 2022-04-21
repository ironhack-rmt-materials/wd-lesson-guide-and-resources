

# Node - Custom Middleware


## Custom middleware for user authorization

@students: 
- students portal includes a very detailed explanation, they may find it useful (login process, sessions, etc  )


Explain:
- middleware
- custom middleware
- middleware as an intermediate argument in our routes. eg:
  
  ```
  router.get('/admin', isUserLoggedIn, () => {
    ...
  })
  ```

Make an example with different roles (eg. req.user.admin, req.user.collaborator):
- create middleware functions in the directory `/middleware` (note: in assessment they are in `/utils/middleware`).
- protect our routes. eg: GET `/create-thing`, GET `/delete-thing`
- if not allowed, redirect to login




## Ironlauncher with Auth boilerplate

```
npx ironLauncher --auth my-project
```

- Demo: run & explain what it has created
  -- /routes/auth.js
  -- /middlewares
  -- /config/index.js added configuration for sessions
  -- installed bcryptjs, connect-mongo and express-session


- Students can use that to generate project-2

