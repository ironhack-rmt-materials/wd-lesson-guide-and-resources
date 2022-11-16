

# React - Token-Based Authentication II (Frontend)


<!-- 

status: draft 

students portal: highlighted


Methodology:
- follow steps on students portal & get code from there
- make sure students understand
- ALTERNATIVE: ask students to do self-guided (at least some parts)



-->


New topics introduced in this unit:
- (context API)
- local storage for the token
- send token in headers of http request with axios ("Set Request Headers")
- Private Pages



Sections in the student portal:
- Auth Context
  > NOTE: refresh context API (provider + consumer)
- Sign Up Page
  - Create the Signup Page (component with form, w/o sending request)
  - Send a Sign Up Request
    > NOTE: if axios request fails, error message is available in `error.response.data.message`
    > NOTE 2: make sure we're consistent when we send errors from the API (in the students portal we have the property "message" + ironlauncher sends them in the property "errorMessage")
  - Render the SignupPage Component
- Login Page
  - Create the Login Page
  - Send a Login Request with axios
- Set up the Authentication Logic
  - Save the Token in the localStorage
    > EXPLAIN: localStorage
    - mdn: https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage
    > NOTE: we could also store the token in state instead of localStorage (but if user refreshes the page it will not be logged in)
  - Verify the Token upon Login
    > EXPLANATION:
      - token now stored in local storage
      - we may still want to check against backend (eg. if the app reloads)
  - Verify the Token upon Initial App Load
    - if the user reloads the page and there's a token in local storage, we want to  "login the user"
  - Remove the Token on Logout
  - Update the Logout button in the Navbar
- Custom route components
  - Private Pages
  - Anonymous Pages (available only if you are NOT logged in)
  - Establish Public and Private Pages
- (Extra) Do not display "delete" button if user not logged in  
  - (conditional rendering)
- Set Request Headers
  (for all requests to the api, we need to send JWT in the header)



## Extra challenges and improvements:
- After signup, automatically login the user
- Add a component library
  - some examples: React Bootstrap, Semantic UI, Ant Design, Chakra, Material UI (MUI)


