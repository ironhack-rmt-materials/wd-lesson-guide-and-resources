
# SQL - Table Relationships & Joins

<!-- 

status: draft

@todo: 
- improve the section for sql joins (for the examples, it'd be interesting to add a table "categories" with categories for products)


Methodology:
- Explain all these concepts based on this example: https://gist.github.com/luisjunco/a3c7dc8a8a8c3468bd387e4f3acbd107


-->



## Database Normalization

Database normalization is a process used in relational databases (SQL databases) to organize data to reduce redundancy and improve data integrity.


In this lesson, we will focus on the practical aspects of database normalization:
- setting constraints on table columns, and 
- establishing relationships between tables using primary and foreign keys.


## Constraints in SQL

- `PRIMARY KEY`: Ensures that each row in a table is uniquely identified.
- `NOT NULL`: Ensures that a column cannot contain NULL values.
- `FOREIGN KEY`: Establishes a relationship between two tables by referencing a column in one table to a column in another table.
- `UNIQUE`: Ensures that all values in a column are unique.
- `CHECK`: Ensures that all values in a column meet a specific condition.
- `DEFAULT`: Provides a default value for a column when no value is specified.



## Joins

- In relational databases, JOIN operations (known as Joins) are used to combine rows from two or more tables with related data into one.

- A JOIN operation allows you to join data from two or more tables based on a related column between them. This related column is typically the primary key in one table and a foreign key in another table.



## SQL Joins Cheatsheets


![cheatsheet - sql joins - 1](./img%20-%20sql%20joins%201.png)

![cheatsheet - sql joins - 2](./img%20-%20sql%20joins%202.png)

- Other diagrams: 
    - https://miro.medium.com/v2/resize:fit:1400/0*gdxxtAKE9vYAjXBk.png
    - https://www.ml4devs.com/images/illustrations/sql-joins-cheatsheet.png
    - https://diegobittencourt.org/wp-content/uploads/2024/06/image.png

- Also useful (detailed cheat sheet): https://images.datacamp.com/image/upload/v1679944084/Joining_Data_in_SQL_458a8fa873.png




### FULL JOIN

- Definition: Returns all rows when there is a match in either table. Rows with no match in one table will have NULL for the columns of the other table.
- Behavior: Combines the results of LEFT JOIN and RIGHT JOIN.
- Use Case: When you want to include all rows from both tables, regardless of whether there’s a match.


Example:

    ```sql
    SELECT * FROM orders AS o FULL JOIN users as u ON o.user_id = u.user_id;
    ```


### LEFT JOIN

- Definition: Returns all rows from the left table (the one before JOIN) and the matching rows from the right table. If there is no match, it fills the right table's columns with NULL.
- Behavior: Includes all rows from the left table regardless of whether there's a match in the right table.
- Use Case: When you want to include unmatched rows from the left table in the result.

Example: get the orders made by each user

    ```sql
    SELECT users.user_id, users.name, orders.order_id, orders.product_id, orders.quantity, orders.total_amount
    FROM users
    LEFT JOIN orders ON users.user_id = orders.user_id;
    ```



### RIGHT JOIN

- Definition: Returns all rows from the right table (the one after JOIN) and the matching rows from the left table. If there is no match, it fills the left table's columns with NULL.
- Behavior: Includes all rows from the right table regardless of whether there's a match in the left table.
- Use Case: When you want to include unmatched rows from the right table in the result.





### INNER JOIN:

- Definition: Returns only the rows where there is a match between the two tables in the specified join condition.
- Behavior: Excludes rows from both tables that do not meet the condition.
- Use Case: When you need data that exists in both tables.

Example: 

    ```sql
    SELECT 
        u.name AS user_name,
        p.title AS product_title,
        o.quantity,
        o.total_amount,
        o.created_at AS order_date
    FROM 
        orders AS o
    INNER JOIN 
        users AS u ON o.user_id = u.user_id
    INNER JOIN 
        products AS p ON o.product_id = p.product_id;
    ```


## Practice

The SQL Murder Mystery (basic queries + joins):
- https://mystery.knightlab.com/walkthrough.html

