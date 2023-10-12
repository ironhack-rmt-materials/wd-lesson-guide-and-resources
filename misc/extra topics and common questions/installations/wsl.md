

# WSL


Check WSL versions: 
- on Powershell, run `wsl -l -v`

Change WSL version (if already installed)
- Run Powershell as admin and change with `wsl --set-version ubuntu 2`



## (Issie) Can not install WSL 2

One common issue is not having Virtualization enabled.
See here: https://github.com/microsoft/WSL/issues/4766#issuecomment-566171621



## (Issue) Nodemon not listening for changes on WSL 2

- Run `nodemon -L`

- Other options: https://stackoverflow.com/a/63455155/11298742