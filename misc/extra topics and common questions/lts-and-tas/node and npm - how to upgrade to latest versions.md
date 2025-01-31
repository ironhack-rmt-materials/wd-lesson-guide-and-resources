
# How to upgrade Node and NPM to latest versions


NVM:

- nvm install x.x.x (ex. `nvm install 22.13.0`)
- nvm alias default x.x.x (ex.`nvm alias default 22.13.0`)

- other useful commands: 
  - nvm ls
  - nvm use x.x.x


NPM:
- upgrading node will upgrade npm
- it seems it is also possible to do it with nvm: https://stackoverflow.com/a/33575448/11298742



## Common issues:

- "nvm keeps 'forgetting' node in new terminal session"
  - this worked for me: https://stackoverflow.com/a/31859164/11298742