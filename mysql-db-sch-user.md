![MySQL Tinitiate Image](mysql_tinitiate.png)

# MySQL
&copy; TINITIATE.COM

##### [Back To Context](./README.md)

# Database, Schema, and User
* In MySQL, a database serves as a structured collection of data.
* A schema acts as a logical container for organizing and grouping database objects, such as tables, views, and stored procedures.
* Lastly, a user in MySQL is an entity that holds access rights to interact with the MySQL system and its databases.
* To make it even short:
    * MySQL software is called the server
    * In a server, we can create multiple databases
    * Each database has logical grouping of database objects called Schema
    * The schema within a database can be accessed by users, which are the individual user logins.

## Database:
* In MySQL, a database is a structured collection of data that is organized and managed for easy access and retrieval.
* It stores tables, views, stored procedures, and other objects that define the schema and structure of the data.
* Within a MySQL server, you can create multiple databases to organize your data.
```sql
-- Create database tinitiate
CREATE DATABASE tinitiate;

-- Use the database
USE tinitiate;

-- MySQL commands are generally case-insensitive
-- We can use uppercase or lowercase or mix of both for commands
-- But for best practice stick to any one format
```
## User:
* In MySQL, users are individual logins that can access the database objects within a schema.
* These users are granted permissions to interact with specific databases and schemas as per the database administrator's configuration.
```sql
-- Step 1:
-- Create a user named 'tiuser' with the password 'Tinitiate!23'
CREATE USER 'tiuser'@'localhost' IDENTIFIED BY 'Tinitiate!23';

-- Step 2:
-- Create a user named 'developer' with the password 'Tinitiate!23'
CREATE USER 'developer'@'localhost' IDENTIFIED BY 'Tinitiate!23';

-- Step 3:
-- Grant privileges to the users on the tinitiate database
GRANT ALL PRIVILEGES ON tinitiate.* TO 'tiuser'@'localhost';
GRANT ALL PRIVILEGES ON tinitiate.* TO 'developer'@'localhost';

-- Step 4:
-- Apply the changes
FLUSH PRIVILEGES;
```
## Schema:
* Each database contains a logical grouping of database objects called schemas.
* But in MySQL, however, schema and database are synonymous, meaning there is no clear distinction between the two.
* Creating a schema in MySQL effectively creates a new database.
```sql
-- Use the Database where you want to create the schema
USE tinitiate;

-- Create the schema (In MySQL, schema and database are synonymous)
CREATE SCHEMA employees;

-- In MySQL, the concept of schema is similar to a database. 
-- The above statement creates a new database named 'employees'.

-- To create tables in the schema (employees)
USE employees;
```

##### [Back To Context](./README.md)
***
| &copy; TINITIATE.COM |
|----------------------|