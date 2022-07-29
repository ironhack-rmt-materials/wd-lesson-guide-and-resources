# LAB | React IronBeers

[REPO](https://github.com/ironhack-labs/lab-react-ironbeers)
[SOLUTION]()

# SETUP

npm i
npm i axios
npm i react-router-dom

- Do not forget BrowserRouter in index.js

# TIPS

Before iteration 1, create all your routes in app.js

- Use `Routes` & `Route` in App component
    ```
    <Routes>
        <Route path="/" element={<LandingPage />}/>
        <Route path="" element={<AllBeers beersList={beersArr}/>}/>
        <Route/>
    </Routes>
    ```
- use `Link` in other components

IT 1.

- how to use images for landing page
  1.  just import them from assets
      - import beer from '../assets/beers.png';
      - and use it like this -> {beer}
  2.  add them to public folder
      - ./images/beers.png

IT 2.

- create a Header component, and import + redner it where you need

IT 3.

- call API in App.js and send the list of beers down through props
- conditional rendering to check if you have the list ready.
  -> create `Spinner` component
  -> render if beerList is not ready
  -> example https://loading.io/css/

IT 4.

- in AllBeers.js you can use object id for the Link
- in SingleBeer.js you should use useParams + call API

IT 6.

# FORM

## CREATING AND HANDLING FORM

    - define the state
        - one state per input
        - state with one object with all the inputs
    - handle form
        - read input value
        - update the state
        - create new object and save it
        - reset the form

## STATE IN FORM. one vs many states

### STATE EXAMPLE 1 (one state - an object)

#### defining state
  const [newBeer, setNewBeer] = useState({
    name: '',
    tagline: '',
    description: '',
    etc.
  });

#### defining input
    <label>
        Name
        type="text" 
        name="name" 
        value={newBeer.name} 
        onChange={(e) => handleInputChange(e)} />
    </label>

    const handleFormSubmit = (e) => {
    e.preventDefault();
    axios.post('https://ih-beers-api2.herokuapp.com/beers/new', newBeer)

#### handle inputs:
    SYNTAX #1

    const handleInputChange = (e) => {
        setNewBeer({ ...newBeer, [e.target.name]: e.target.value });
    };

    SYNTAX #2

    const handleInputChange = (e) => {
        const { value, name } = e.target;
        setNewBeer({...newBeer, [name]: value})
    };

### STATE EXAMPLE 2 (many states)

#### defining state
    const [name, setName] = useState("");
    const [tagline, setTagline] = useState("");
    const [description, setDescription] = useState("");
    etc

#### defining input
        type="text"
        name="name"
        value={name}
        onChange={(e) => setName(e.target.value)}

#### handle inputs:
    const handleSubmit = (e) => {
        e.preventDefault();
        const body = { name, tagline, description, firstBrewed, brewersTips, ibu, contributed};

        axios
            .post("https://ih-beers-api2.herokuapp.com/beers/new", body)


# EXTRA NOTES

### useEffect() 2nd argument:

You can control when you want code to be repeated

useEffect(() => {}, []); // runs after component is rendered first
useEffect(() => {}, [beersList]); // runs every time beersList gets updated


### NAVLINK vs ROUTES

- `NavLink` is just a clickable link -> it does not hold information.
- Link and Route correlates and it is enough to pass information/render components in `Routes` as long as paths match

### LINK VS <a>

- In react always use `Link` instead of `a`
- Link tag will render a semantically valid a tag, but doesn’t refresh the page
