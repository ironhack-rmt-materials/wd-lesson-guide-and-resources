


# "React - Building the Rest API" - things to fix in the students portal


Affects:
- "React | Building the Rest API"
  - students portal x2
  - repo with final result from students portal x1


Fix:
- [ ] send correct status codes (201, 500.....)

IMPROVEMENTS:
- [ ] error handling (clg + status code)
- [ ] remove redundant status codes
- [ ] models with required.

```js
        .catch(err => {
            console.log("Error creating new project...", err);
            res.status(500).json({
                message: "Error creating a new project",
                error: err
            });
        });
```

```js
.then(project => res.status(200).json(project))
```