![MySQL Tinitiate Image](mysql_tinitiate.png)

# MySQL
&copy; TINITIATE.COM

##### [Back To Context](./README.md)

# DQL - Set Operations
* Set operations in SQL are used to combine or compare the results of two or more queries.
* These are essential for manipulating and combining data from multiple tables.
* The main set operations include UNION, INTERSECT, and EXCEPT. 

## Set Operations in SQL Server:
### UNION:
* The UNION operator is used to combine the results of two or more SELECT statements into a single result set.
* It returns all distinct rows from both result sets. It removes duplicate rows by default.
```sql
-- Retrieve unique department numbers from both the employees
-- and projects tables
SELECT deptno FROM employees.emp
UNION
SELECT projectno AS deptno FROM employees.projects;

-- Retrieve unique employee names and project names from both the employees
-- and projects tables
SELECT ename AS name FROM employees.emp
UNION
SELECT CONCAT('Project: ', projectno) AS name FROM employees.projects;

-- Combine the names of employees, departments, and projects
SELECT ename AS name FROM employees.emp
UNION
SELECT dname AS name FROM employees.dept
UNION
SELECT projectno AS name FROM employees.projects;

-- UNION ALL: This operator does same as UNION with including duplicate rows
-- Retrieve all department numbers from both the employees
-- and projects tables
SELECT deptno FROM employees.emp
UNION ALL
SELECT projectno AS deptno FROM employees.projects;
```
### INTERSECT(Simulated using INNER JOIN):
* MySQL does not support the INTERSECT operator directly, but it can be simulated using an INNER JOIN.
* The INTERSECT operator is used to retrieve the common rows that appear in the result sets of two or more SELECT statements.
```sql
-- Retrieve grade numbers that exist in both the employees
-- and projects tables
SELECT grade FROM employees.salgrade sg
INNER JOIN (SELECT projectno FROM employees.projects) p
ON sg.grade = p.projectno;

-- Retrieve employee names that exist in both the employees
-- and projects tables
SELECT ename AS name FROM employees.emp e
INNER JOIN (SELECT CONCAT('Project: ', projectno) AS name FROM employees.projects) p
ON e.ename = p.name;
```
### EXCEPT (Simulated using LEFT JOIN and IS NULL):
* MySQL does not support the EXCEPT operator directly, but it can be simulated using a LEFT JOIN and checking for NULL values.
* The EXCEPT operator is used to retrieve the rows that appear in the first result set but not in the result sets of one or more subsequent SELECT statements.
```sql
-- Retrieve empno numbers from the employees table that
-- do not exist in the emp_projects table
SELECT e.empno FROM employees.emp e
LEFT JOIN employees.emp_projects ep ON e.empno = ep.empno
WHERE ep.empno IS NULL;
```

##### [Back To Context](./README.md)
***
| &copy; TINITIATE.COM |
|----------------------|