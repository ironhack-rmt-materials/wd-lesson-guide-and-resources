

# HTML date - prepopulate with data from mongoose


Mongoose Schema:


```js
const recipeSchema = new Schema(
  {

    //...

    date: {
      type: Date,
    },

    //...
  }
```


Route:


```js

router.get("/recipe/:recipeId/edit", (req, res, next) => {

    //....
    //....

    Recipe.findById(id)
        .then(recipeDetails => {

            // converts this document into a plain-old JavaScript object
            // (mongoose returns a document, with .toObject(), we're converting it to a real JS object)
            recipeDetails = recipeDetails.toObject();

            // convert date format to something that we can use in an html date
            // source: https://stackoverflow.com/a/29774197/11298742
            recipeDetails.date = recipeDetails.date.toISOString().split('T')[0]


            res.render("income/edit-income", recipeDetails)
        })
        .catch((e) => {
            //...
        });
});
```


Notes:


HTML date and time formats:
- https://developer.mozilla.org/en-US/docs/Web/HTML/Date_and_time_formats#local_date_and_time_strings
