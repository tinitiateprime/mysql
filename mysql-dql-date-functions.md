![MySQL Tinitiate Image](mysql_tinitiate.png)

# MySQL
&copy; TINITIATE.COM

##### [Back To Context](./README.md)

# DQL - Date Functions
* Date functions in SQL Server are used to perform various operations on date and timestamp data stored in the database.
* They allow for manipulation, extraction, formatting, and calculation of dates and times.

## Date functions in MySQL:
### Current Date and Time (NOW):
* Returns the current date and time.
```sql
-- Retrieve the current date and time
SELECT NOW();
```
### Extract Function (EXTRACT):
* Returns a specific component (such as year, month, day) from a date or timestamp.
```sql
-- Retrieve the day of the month from the 'hiredate' column
SELECT EXTRACT(DAY FROM hiredate) FROM employees.emp;
```
### Date Difference Function (DATEDIFF):
* Calculates the difference between two dates, returning the result as an interval in days.
```sql
-- Calculate the age of each employee based on their 'hiredate'
SELECT DATEDIFF(CURDATE(), hiredate) FROM employees.emp;
```
### Date Addition/Subtraction:
* Adds or subtracts a specified interval (such as days, months) from a date or timestamp.
```sql
-- Add a specific number of days to a date
SELECT hiredate + INTERVAL 7 DAY FROM employees.emp;

-- Subtract 6 months from the 'hiredate' column in the employees table
SELECT hiredate - INTERVAL 6 MONTH FROM employees.emp;
```
### Date Formatting (DATE_FORMAT):
* Formats a date or timestamp according to a specified format.
```sql
-- Format the 'hiredate' column in a specific date format
SELECT DATE_FORMAT(hiredate, '%Y-%m-%d') FROM employees.emp;
```
### Weekday Function (DAYOFWEEK):
* Returns the day of the week (1 for Sunday, 2 for Monday, etc.) from a date or timestamp.
```sql
-- Retrieve the day of the week (1 for Sunday, 2 for Monday, etc.) from the 'hiredate' column
SELECT DAYOFWEEK(hiredate) FROM employees.emp;
```
### Date to String (Various formats):
* You can convert a date to a string in various formats using the DATE_FORMAT function.
```sql
-- YYYY-MM-DD:
SELECT DATE_FORMAT(hiredate, '%Y-%m-%d') AS hiredate
FROM employees.emp;

-- MM/DD/YYYY:
SELECT DATE_FORMAT(hiredate, '%m/%d/%Y') AS hiredate
FROM employees.emp;

-- DD/MM/YYYY:
SELECT DATE_FORMAT(hiredate, '%d/%m/%Y') AS hiredate
FROM employees.emp;

-- Mon DD, YYYY:
SELECT DATE_FORMAT(hiredate, '%b %d, %Y') AS hiredate
FROM employees.emp;

-- YYYYMMDD:
SELECT DATE_FORMAT(hiredate, '%Y%m%d') AS hiredate
FROM employees.emp;

-- DD-MM-YYYY:
SELECT DATE_FORMAT(hiredate, '%d-%m-%Y') AS hiredate
FROM employees.emp;

-- YYYY/MM/DD:
SELECT DATE_FORMAT(hiredate, '%Y/%m/%d') AS hiredate
FROM employees.emp;

-- DD MMM YYYY:
SELECT DATE_FORMAT(hiredate, '%d %b %Y') AS hiredate
FROM employees.emp;
```
### DateTime to String (Various formats):
* To convert a datetime to a string in various formats in MySQL, you can use the DATE_FORMAT function.
```sql
-- YYYY-MM-DD HH:MI:SS:
SELECT DATE_FORMAT(hiredate, '%Y-%m-%d %H:%i:%s') AS hiredate
FROM employees.emp;

-- Using NOW()
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d %H:%i:%s') AS datetimetostring;

-- YYYY-MM-DD HH:MI:SS:MMM:
SELECT DATE_FORMAT(NOW(), '%Y-%m-%d %H:%i:%s.%f') AS datetimetostring;

-- DD Mon YYYY HH:MI:SS:MMM:
SELECT DATE_FORMAT(NOW(), '%d %b %Y %H:%i:%s.%f') AS datetimetostring;

-- Mon DD YYYY HH:MI:SS:MMM AM (or PM):
SELECT DATE_FORMAT(NOW(), '%b %d %Y %h:%i:%s:%f %p') AS datetimetostring;
```
### String to Date (Various formats):
* You can convert a string in various formats to a date using the STR_TO_DATE function.
```sql
-- YYYY-MM-DD:
SELECT STR_TO_DATE('2023-04-15', '%Y-%m-%d') AS date;

-- MM/DD/YYYY:
SELECT STR_TO_DATE('04/15/2023', '%m/%d/%Y') AS date;

-- DD.MM.YYYY:
SELECT STR_TO_DATE('15.04.2023', '%d.%m.%Y') AS date;

-- Mon DD, YYYY:
SELECT STR_TO_DATE('Apr 15, 2023', '%b %d, %Y') AS date;

-- YYYYMMDD:
SELECT STR_TO_DATE('20230415', '%Y%m%d') AS date;
```
### String to DateTime (Various formats):
* You can convert a string in various formats to a datetime using the STR_TO_DATE function.
```sql
-- YYYY-MM-DD HH:MI:SS:
SELECT STR_TO_DATE('2023-04-15 13:30:45', '%Y-%m-%d %H:%i:%s') AS datetime;

-- MM/DD/YYYY HH:MI:SS:
SELECT STR_TO_DATE('04/15/2023 13:30:45', '%m/%d/%Y %H:%i:%s') AS datetime;

-- DD.MM.YYYY HH:MI:SS:
SELECT STR_TO_DATE('15.04.2023 13:30:45', '%d.%m.%Y %H:%i:%s') AS datetime;

-- Mon DD YYYY HH:MI:SS:MMM:
SELECT STR_TO_DATE('Apr 15 2023 01:30:45:375', '%b %d %Y %h:%i:%s:%f') AS datetime;

-- YYYYMMDD HH:MI:SS:
SELECT STR_TO_DATE('20230415 13:30:45', '%Y%m%d %H:%i:%s') AS datetime;
```
### DateTime and TimeZone:
#### Date, Timezones, UTC, and Offsets:
* **Date and Time**: In computing, dates and times are represented using various data types. A common approach is to use a datetime data type that includes both date and time information.
* **Timezones**: Timezones are regions of the Earth that have the same standard time. Each timezone is usually offset from Coordinated Universal Time (UTC) by a certain number of hours and minutes. For example, Eastern Standard Time (EST) is UTC-5, meaning it is 5 hours behind UTC.
* **UTC**: Coordinated Universal Time (UTC) is the primary time standard by which the world regulates clocks and time. It is not adjusted for daylight saving time. UTC is often used as a reference point for converting between different timezones.
* **Offsets**: An offset is the difference in time between a specific timezone and UTC. It is usually expressed as a positive or negative number of hours and minutes. For example, UTC+2 means the timezone is 2 hours ahead of UTC, while UTC-8 means the timezone is 8 hours behind UTC.
* **Applying an Offset to a Date Datatype Column**: To apply an offset to a date datatype column in MySQL, you can use the DATE_ADD function to add or subtract a specific number of hours to/from the column value. For example, to add 5 hours to a datetime column named hiredate, you can use the following query:
```sql
-- This query will return the value of hiredate adjusted by 5 hours. 
SELECT DATE_ADD(hiredate, INTERVAL 5 HOUR) AS adjusted_datetime
FROM employees.emp;
```
#### Cast a DateTime to DateTime with Timezone (in UTC, EST and IST TimeZones):
* Create a date time variable and cast it as a DateTime with TimeZone data type
* Here we cast it at different TimeZones (UTC, EST and IST)
* Demonstration in SQL
```sql
SELECT 
    '2024-04-17 15:30:00' AS OriginalDateTime,
    CONVERT_TZ('2024-04-17 15:30:00', '+00:00', '+00:00') AS UTCDateTime,
    CONVERT_TZ('2024-04-17 15:30:00', '+00:00', '-05:00') AS ESTDateTime,
    CONVERT_TZ('2024-04-17 15:30:00', '+00:00', '+05:30') AS ISTDateTime;
```
### Cast a DateTime Timezone to Another TimeZone
```sql
-- Convert from UTC to EST
SELECT 
    'UTCDateTime: ' AS Description, 
    CONVERT_TZ('2024-04-17 15:30:00', '+00:00', '+00:00') AS UTCDateTime 
UNION ALL
-- Convert the above UTC time to EST
SELECT 
    'ESTDateTime: ' AS Description, 
    CONVERT_TZ(CONVERT_TZ('2024-04-17 15:30:00', '+00:00', '+00:00'), '+00:00', '-05:00') AS ESTDateTime;
```

##### [Back To Context](./README.md)
***
| &copy; TINITIATE.COM |
|----------------------|