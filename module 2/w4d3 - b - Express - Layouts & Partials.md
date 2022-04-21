
# Express - Layouts & Partials

<!-- 

- Status: draft (many things incomplete)

- Notes:
  - Partials take quite a bit to explain if we do codealong (just mention them)

-->


## Intro

- Explain layouts with an example (codealong): we're going to add a navigation menu at the top of all pages
  - Do that (codealong), repeating the code for all pages/views


## Layouts



- layout.hbs: `{{{ body }}}`
  
  - IMPORTANT: notice the "TRIPLE" curly brace

    ```
    <!DOCTYPE html>
    <html lang="en">
    <head>
    </head>

    <body>

        {{{ body }}}

    </body>
    </html>
    ```


## Skipping layouts

- Set `layout: false` in the object we pass to the view

    ```
    app.get("/teams", (req, res, next) => {
        const data = {
            layout: false
        }
        res.render("teams", data);
    });
    ```


## Partials (Bonus / Self guided)

- Configure 

```
hbs.registerPartials(__dirname + "/views/partials");
```

- Create a Partial


- Call a Partial from a View

```
{{> myPartial }}

```


- Passing parameters to partials

```
      {{#each players}} 
        {{> playerCard this}} 
      {{/each}}
```



## Summary

Reuse code for all pages -> layout
Reuse code for pages of the same type -> views
Reuse code inside your views -> partials

