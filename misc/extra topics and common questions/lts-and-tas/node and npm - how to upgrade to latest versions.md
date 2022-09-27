
# How to upgrade Node and NPM to latest versions


If you installed node through nvm, you can do the following:

Node:
- nvm ls
- nvm use x.x.x
- nvm install x.x.x (ex. `nvm install 16.17.0`)


NPM:
- upgrading node will upgrade npm
- it seems it is also possible to do it with nvm: https://stackoverflow.com/a/33575448/11298742



## Common issues:

- "nvm keeps 'forgetting' node in new terminal session"
  - this worked for me: https://stackoverflow.com/a/31859164/11298742