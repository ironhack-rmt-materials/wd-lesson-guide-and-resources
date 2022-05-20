# LAB | MongoDB Advanced Querying

[REPO](https://github.com/ironhack-labs/lab-advance-querying-mongo)

[SOLUTION](https://gist.github.com/IH-WebDev-TA-Remote/9cb43c2f8e2aa0f39b4b9076b94c2176)

### REMIND

- fork
- clone

### Guidelines for LAB

1. unzip the folder with data -> you'll have json file
2. **in labs folder** run command to import db to mongo

```
$ mongoimport --db companiesDB --collection companies --file data.json
```
-  in compass look for the name companiesDB

3. Work in queries.md


@TA:  
- 1st task solution: (show how to write it)
    - Solve in compass, then paste search syntax in queries.md

```
Compass:
 {name: 'Babelgum'}
 {name: 1, _id:0}

Queries.md
 query: { name: 'Babelgum'} 
 projection: { name: 1, \_id: 0 }
 ```