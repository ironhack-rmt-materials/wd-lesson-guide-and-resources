
# SQL Introduction

<!-- 

status: ready.


Summary of the topics covered in this unit:
- postgreSQL installation
- some basic commands

Methodology: 
- do the exercise provided (students will install postgres and discover some basic commands)

-->



## Practice: PostgreSQL setup & first steps

- Instructions: https://gist.github.com/luisjunco/26ffe513a9a40e28c4862234ce274b42

- Time: 20-30min.




## Quick intro to SQL statements

- Create a new db: `CREATE DATABASE animals_db;`
- Get a list of dbs: `\l`
- Connect to our db: `\c animals_db`

- Create a new table:
    ```sql
    CREATE TABLE habitats(
        id INT,
        name VARCHAR(64)
    );
    ```
- Get list of tables: `\dt`

- Create a new row:
    ```sql
    INSERT INTO habitats VALUES (1, 'River');
    INSERT INTO habitats VALUES (1, 'Forest');
    ```

- Get a list of habitats:
    ```sql
    SELECT * from habitats;
    ```



## Install Beekeeper Studio

Install Beekeeper Studio (Community Edition):
- https://www.beekeeperstudio.io/get-community



Notes (Mac users): 
- Mac users often have problems to login on Beekeeper (when they install postgres, it doesn't ask for password)
- To connect on Beekeeper, do the following:
    - Open psql with the command `psql postgres` + get a list of users with `\du`
    - On beekeeper, enter these settings:
        - Username: the user that we got in the previous step
        - Password: leave empty
        - Default database (IMPORTANT): "postgres" 



