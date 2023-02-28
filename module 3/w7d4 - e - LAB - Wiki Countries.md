

# LAB - Wiki Countries




How:
- in Pairs





Main topics:
- Routing (Routes, URL parameters)
- useEffect
- API requests (fetch / axios)

Other topics:
- Bootstrap (focus on the logic and the concepts we have seen today)


Note:
- We use URL parameters (they don't need query string)


Notes to students:
- Leave style, bootstrap, flags etc for the end (focus on practicing the concepts we've seen today)
- Navbar component is not a Route, it's always there!
- If you want to access the name of the country you need `name.common`
- You need the `alpha3code` for the url for each country
- To display all borders .map() over it (it's an array)
- Some countries don't have borders, so you get an empty array.



Common pain points:

- error while data loading (ex. can not read properties of undefined)
  - conditional rendering.




## Iteration 1.4

- Flags: you can skip it (focus on React)



## Iteration 2 | Linking it all together

We load data from `.json`


## Iteration 3 | Fetch countries data from an API

We get data from API



## Iteration 4 | Bonus | Fetch one country data from an API

> "make a request to the RestCountries API and fetch the data for the specific country"

- We do that to practice useEffect and API requests.
- Another alternative would be to pass the details from the parent component through props (`<App>` list of countries with all details).





