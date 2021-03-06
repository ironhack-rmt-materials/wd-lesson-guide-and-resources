
# React - Routing Advanced

<!-- 

Status: notes

-->



## Refresh: URL parameters vs Query String

- URL structure: 
  https://cdn.cognitiveseo.com/blog/wp-content/uploads/2019/11/url-structure-1024x538.jpg

- Examples of Route Params

  https://localhost:3000/countries/42
  https://localhost:3000/artists/madonna
  https://localhost:3000/artists/madonna/albums/5


- Examples of Query String

  https://localhost:3000/rooms?maxPrice=200
  https://localhost:3000/rooms?sort=price




## URL parameters


```javascript
<Routes>
    <Route path="/" element={<HomePage />} />
    <Route path="/characters/:characterId" element={<CharacterDetails />} />
</Routes>
```


```javascript
import { useParams } from "react-router";

function CharacterDetails(props) {
  const {characterId} = useParams();
  // ...
}

```


## Query Strings


Note: 
- for lab wiki countries they don't need query strings
- if short of time, just show on students portal

For query string there's a hook `useSearchParams`:
- https://reactrouter.com/docs/en/v6/api#usesearchparams



## Extra: nested routes

Example of nested routes with React Router:
https://stackblitz.com/edit/react-y43mfi?file=src/App.js