

# Different types of users or user roles


## Challenge

Functionality for different type of accounts.
Examples:
- an application where you have accounts for Regular Users + Admin.
- an application where you can register as a Teacher or as a Student to learn new skills.
- an application where you can register as a Company or as a Job Seeker.


## Options


For some applications, you may not even need different types of users.
- e.g. in some job boards it can make sense that I can publish an offer + also apply
- for example, in a freelance job portal, freelancers sometimes also need to hire people (it wouldn't make sense that I need to create two separate accounts)
- if that's the case, you may want to have some fields that are not required in your user model 




For user roles (e.g. admin vs normal roles), an easy option is the following:
- have a single model (User)
- in that model, have a field for role (e.g. admin, user). 
  - IMPORTANT: set default to "normal" users.
- to have an admin account, change the field manually on the db




For user types, here's some options:
  - option 1: create a model for each type of user
    - disadvantage: you may need to duplicate all auth logic (e.g. register, login)
  - option 2: only one model, on that model we store all the info (some users may have some info, other types of users different info)
    - example: https://stackoverflow.com/a/38628061/11298742
  - option 3: one model with different schemas (using mongoose discriminators)



## Discriminators:


> Discriminators are a schema inheritance mechanism. 

> They enable you to have multiple models with overlapping schemas on top of the same underlying MongoDB collection. rather than different documents.

- If the different roles share properties, one good option is using Discriminators:

Examples (some syntax is a bit different than the one we saw in class):
  - https://stackoverflow.com/a/52768027/11298742
  - https://stackoverflow.com/a/38639516/11298742


Article: 
- https://dev.to/helenasometimes/getting-started-with-mongoose-discriminators-in-expressjs--22m9



Example (project 3):
- https://github.com/miob1781/lobby-hub-server/tree/main/models
- users can create an account as Lobbysts or Politicians

