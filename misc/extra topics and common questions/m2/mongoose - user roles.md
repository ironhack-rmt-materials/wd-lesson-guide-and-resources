

# Allow multiple user roles with Mongoose


- If the different roles share properties, one good option is using Discriminators:

  - https://stackoverflow.com/a/52768027/11298742

  - https://stackoverflow.com/a/38639516/11298742

  - https://stackoverflow.com/a/48165516/11298742


##  Discriminators:

> Discriminators are a schema inheritance mechanism. 

> They enable you to have multiple models with overlapping schemas on top of the same underlying MongoDB collection. rather than different documents.

- https://stackoverflow.com/questions/35361297/inheriting-mongoose-schemas/35366719#35366719

- https://dev.to/helenasometimes/getting-started-with-mongoose-discriminators-in-expressjs--22m9