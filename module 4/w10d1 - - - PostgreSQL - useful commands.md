


# PostgreSQL - Useful commands




## User Management

- `\du`: list all roles (users and groups)



## DB Management

- `\l`: list all databases

- Create a new DB: `CREATE DATABASE new_database;`

- `\c`: connect to a DB



## Table Management

- `\dt`: list all tables in the current DB

- Create a new table: 

    ```sql
    CREATE TABLE users (
        user_id SERIAL PRIMARY KEY,
        name VARCHAR(100),
        email VARCHAR(100) UNIQUE,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );
    ```

- `\d+ [table_name]`: describe a table's structure

- Add a new column to a table: `ALTER TABLE table_name ADD COLUMN column_name data_type;`

- Drop a table from the DB: `DROP TABLE table_name;`



## Adding data


- Add a new row (record):

    ```sql
    INSERT INTO users (name, email, created_at) VALUES ('Alice Smith', 'alice@example.com', '2024-01-15');
    ```

- Alternative (omitting column names):

    ```sql
    INSERT INTO users VALUES (DEFAULT, 'Alice 2', 'alice@example.com', DEFAULT);
    ```


## Querying


- Get all rows from a table: `SELECT * FROM table_name;`

- Get specific columns from a table: `SELECT column1, column2 FROM table_name;`



## Syntax

- Quotes: 
    - Double quotes are used to refer to column names, table names, or identifiers.
    - String literals should be enclosed in single quotes ('), not double quotes ("). 


- Semicolons: 
    - Semicolons indicate the end of a command.
    - They're essential when you're running multiple SQL commands in a single script or session.


- Case Sensitivity:
    - SQL keywords (like CREATE, SELECT, TABLE, etc.) are case-insensitive in PostgreSQL. So, you can use lowercase, uppercase, or a combination of both for SQL commands 
        - e.g., CREATE DATABASE, create database, or Create Database would all work.
    - However, identifiers like table names or column names are case-sensitive if you quote them. By default, PostgreSQL will convert unquoted identifiers to lowercase.


