
# w8d1


- Refresh [0.5h]
  - (skip) How we implement CRUD (example: `Comment`)
  <!-- @LT: can be interesting to show with commentMessage + author -->
    - Model
    - Routes
      - one file per resource
      - rest patterns
      - example: GET /events, POST /events
      - think together post request
  - Authentication
    - Model
    - Endpoint to register (`/signup`)
      - similar to "Create" but we need to create hash
    - Endpoint to login (`/login`)
    - Verify
  - Protected routes with middleware


- React | Context API [1.5h]

- Explain main concepts for the self-guided units [0.5h]
  - see `w8d1 - c - React - Token-Based Authentication II (Frontend).md`

- Self-guided x2 (see below)



## Active Learning / Afternoon

Follow these two units & implement the code:
- "React | Token-Based Authentication II (Frontend)"
- "React | Organizing HTTP Requests"

<!-- How: work in pairs -->

Super bonus:
- Add a component library
- Implement the changes so that the user is automatically logged in when you create an account (in the backend api, you'll need to change the endpoint "/signup" so that, when you create an account, it signs and returns a jwt)

