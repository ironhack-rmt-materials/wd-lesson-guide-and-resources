# Setting up the MongoDB Atlas

1. Create a new project
2. Select the name for the project => Click `Create Project`
3. Select the `FREE` tier => Click `CREATE`
4. Select your Cloud Provider and Region of choice => Click `CREATE CLUSTER` (it's in the bottom of the screen, maybe you need to change resolution, exit full screen view)
5. Set Username/Password for access on the Database.
    1. username: `luis` (example)
    2. password: `iloveunicorns` (example)
6. Click on `CLOUD ENVIRONMENT` => IP Address: `0.0.0.0/0` => Click `ADD ENTRY`
7. Click on `Finish and Close`
8. On `Database` => click on `Connect` => Click on `Connect your application` => Save the URI
9. Open the project on VSCode (ex.: project-management-server)
10. On the `.env` file copy the URI to a variable called `MONGODB_URI` ex.: `mongodb+srv://<username>:<password>@cluster0.hdffjst.mongodb.net/?retryWrites=true&w=majority
`
  10.1. Change the `<username>` for the username you setup on the MongoDB Atlas
  10.2 Change the `<password>` for the password you setup for the mongoDB atlas

```env
  MONGODB_URI = mongodb+srv://luis:iloveunicorns@cluster0.hdffjst.mongodb.net/?retryWrites=true&w=majority
```
[Gist](https://gist.github.com/TA-Remote/80801bf13ce27844e1b5b50f858436c7)