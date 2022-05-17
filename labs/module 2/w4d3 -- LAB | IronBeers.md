# LAB | IronBeers

[REPO](https://github.com/ironhack-labs/lab-ironbeers)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/24857da3fb87a86b65e0ff750c28b1ba)

### REMIND

- fork
- clone

### Guidelines for LAB

- npm install
- run nodemon app.js (instead of node app.js)  
  <br>
- working with PunkAPI / npm package
  - this API communicates with a remote database
  - no need to install it

GOAL

- practice handlebars (res.render)
     - layouts
     - partials (bonus)
- practice reading documentation!

## TIPS

- layout.hbs is your initial file -> not index.hbs
- all the routes go into app.js  
<br>
@TA:
- Show example how to start creating routes:
	- punkApi is a class
	- console.log()

- creating route + making get request
```
app.get('/beers', (req,res) => {
```

- making query to API
```
  punkAPI
    .getBeers()
    .then((result) => {
	console.log(result);
	res.render('beers', result)
	// res.render('beers', {objectName: result})
	)
    .catch()
});
```

### COMMON MISTAKES

 -> slash vs no slash
 -> using 'this' vs 'specificName'

BONUS ITERATION 6 & 7
- 6. create partials
- 7. req.params

