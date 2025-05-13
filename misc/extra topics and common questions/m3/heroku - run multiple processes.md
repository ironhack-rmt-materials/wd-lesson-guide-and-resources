

# Heroku - Run multiple processes

- create a `Procfile` (https://devcenter.heroku.com/articles/procfile)
- configure heroku to run more than one process:
  - e.g.: `heroku ps:scale worker=1`
  - details: https://stackoverflow.com/a/22991644/11298742

note: it is possible to have as many as you want but free account allows max 2.

