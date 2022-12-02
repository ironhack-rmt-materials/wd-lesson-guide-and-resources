
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


- create `layout.hbs`
- inside layout.hbs, add `{{{ body }}}`
  
  - IMPORTANT: notice the "TRIPLE" curly brace

    ```hbs
      <!DOCTYPE html>
      <html lang="en">
      <head>
      </head>

      <body>

          {{{ body }}}

      </body>
      </html>
    ```


## (Extra) Skipping layouts

- Set `layout: false` in the object we pass to the view

    ```javascript
    app.get("/teams", (req, res, next) => {
        const data = {
            layout: false
        }
        res.render("teams", data);
    });
    ```


## Partials (Bonus / Self guided)

- Configure 

  ```javascript
    const hbs = require("hbs");

    // ...

    hbs.registerPartials(__dirname + "/views/partials");
  ```

- Create a Partial (ex. banner / list with other products / contact form)


- Call a Partial from a View

  ```hbs
    {{> myPartial }}
  ```

- Note: 
  - use `camelCase.hbs` for names of partials (`kebab-case.hbs` will not work)


- Passing parameters to partials

  ```hbs
    {{#each players}} 
      {{> playerCard this}} 
    {{/each}}
  ```



## Summary

Reuse code for all pages → Layout
Reuse code for pages of the same type → Views
Reuse code inside your views → Partials

