![MySQL Tinitiate Image](mysql_tinitiate.png)

# MySQL
&copy; TINITIATE.COM

##### [Back To Context](./README.md)

# DDL - Data Definition Language
* In MySQL, DDL (Data Definition Language) encompasses a group of SQL commands that are used to create, modify, and remove the structure of database objects. These objects include tables, indexes, views, schemas, sequences, and more.
* DDL statements are crucial for establishing the database schema, defining relationships between tables, and ensuring data integrity. They serve as the foundation for organizing and managing data within MySQL databases.

## Primary DDL commands in MySQL:
### CREATE:
* Used to create new database objects such as tables, indexes, views, schemas, sequences, and other objects.
```sql
-- Schema DDL
CREATE DATABASE emp;
CREATE USER 'ti'@'localhost' IDENTIFIED BY 'Tinitiate!23';
GRANT ALL PRIVILEGES ON emp.* TO 'ti'@'localhost';

-- Set the schema where you want to create the DB objects
USE emp;

-- DDL Create Command
-- Create dept table
CREATE TABLE dept (
    deptid  INT,
    dname   VARCHAR(100)
);

-- Create emp table
CREATE TABLE emp (
    empid    INT,
    ename    VARCHAR(100),
    sal      DECIMAL(7,2),
    deptid   INT
);

-- Create projects table
CREATE TABLE projects (
    ProjectID      INT,
    ProjectName    VARCHAR(100),
    ProjectBudget  DECIMAL(12,2)
);

-- Create empprojects table
CREATE TABLE EmpProjects (
    EP_ID       INT,
    EmpID       INT,
    ProjectID   INT,
    StartDate   DATE,
    EndDate     DATE
);
```

### ALTER:
* Modifies the structure of existing database objects, such as adding or dropping columns from a table.
```sql
-- Alter table "emp": Add a new column called "hire_date" of type DATE.
ALTER TABLE emp ADD hire_date DATE;
-- To change back to previous
ALTER TABLE emp DROP COLUMN hire_date;

-- Alter table "projects":
-- Change the data type of the column "ProjectBudget" to DECIMAL(12,2).
ALTER TABLE projects MODIFY COLUMN ProjectBudget DECIMAL(12,2);
-- To change back to previous
ALTER TABLE projects MODIFY COLUMN ProjectBudget DECIMAL(12,2);

-- Alter table "EmpProjects": Drop the column "EndDate".
ALTER TABLE EmpProjects DROP COLUMN EndDate;
-- To change back to previous
ALTER TABLE EmpProjects ADD COLUMN EndDate DATE;
```

### DROP:
* Deletes existing database objects, such as tables, indexes, or views.
```sql
-- To drop dept table in emp schema
DROP TABLE dept;

-- To again create it
CREATE TABLE dept (
    deptid  INT,
    dname   VARCHAR(100)
);
```

##### [Back To Context](./README.md)
***
| &copy; TINITIATE.COM |
|----------------------|