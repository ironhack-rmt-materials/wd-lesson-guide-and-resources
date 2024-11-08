


Issue: not possible to connect to MongoDB on Mac.



## Option 1. Try running the service:

brew services stop mongodb-community
brew services start mongodb-community


## Option 2. Install an older version of mongodb-community

This may be needed for older versions of Mac.

Source:
  https://stackoverflow.com/questions/57856809/installing-mongodb-with-homebrew/59872332#59872332


Steps to follow:
- brew services stop mongodb-community
- brew uninstall mongodb/brew/mongodb-community
- brew tap mongodb/brew
- brew install mongodb-community@4.4
  - note: after installing, instructions to create a symlink will be given in the CLI.
- brew services start mongodb/brew/mongodb-community@4.4


## Check MongoDB Logs

- tail -n 100 /usr/local/var/log/mongodb/mongo.log


