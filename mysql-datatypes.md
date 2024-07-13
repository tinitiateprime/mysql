![MySQL Tinitiate Image](mysql_tinitiate.png)

# MySQL
&copy; TINITIATE.COM

##### [Back To Context](./README.md)

# MySQL Data Types
* MySQL provides a variety of data types, each with unique strengths and limitations.

## Commonly used data types in MySQL:
* **Numeric** data types are used to store numbers. There are several different numeric data types available, each with its own range and precision. The most common numeric data types are:

    * **INT** - Stores whole numbers from -2147483648 to 2147483647. 
        * **Example:** `quantity INT`.

    * **BIGINT** - Stores whole numbers from -9223372036854775808 to 9223372036854775807. 
        * **Example:** `employee_id BIGINT`.
    * **DECIMAL** - Stores numbers with a fixed number of decimal places. For example, DECIMAL(10,2) can store numbers from -99999999.99 to 99999999.99. 
        * **Example:** `price DECIMAL(10,2)`.
    * **NUMERIC** - Stores numbers with a variable number of decimal places. Equivalent to DECIMAL.
        * **Example:** `quantity NUMERIC(7,2)`.
    * **FLOAT** - Stores single-precision floating-point numbers.
        * **Example:** `temperature FLOAT`.
    * **DOUBLE** - Stores double-precision floating-point numbers.
        * **Example:** `latitude DOUBLE`.

* **Date and Time** data types are used to store dates and times. The most common date and time data types are:
    * **DATE** - Stores a date in the format YYYY-MM-DD. 
        * **Example:** `birthdate DATE`.

    * **DATETIME** - Stores a date and time in the format YYYY-MM-DD HH:MM:SS. 
        * **Example:** `created_at DATETIME`.
    * **TIMESTAMP** - Stores a date and time in the format YYYY-MM-DD HH:MM:SS. Automatically updates to the current timestamp.
        * **Example:** `last_modified TIMESTAMP`.
    * **TIME** - Stores a time of day in the format HH:MM:SS. 
        * **Example:** `appointment_time TIME`.
    * **YEAR** - Stores a year in the format YYYY.
        * **Example:** `graduation_year YEAR`.

* **String** data types are used to store text. The most common string data types are:
    * **CHAR(n)** - Stores a fixed-length string of length n. 
        * **Example:** `country_code CHAR(2)`.

    * **VARCHAR(n)** - Stores a variable-length string with a maximum length of n. 
        * **Example:** `name VARCHAR(255)`.
    * **TEXT** - Stores variable-length strings with a maximum length of 65,535 characters. 
        * **Example:** `description TEXT`.
    * **TINYTEXT** - Stores variable-length strings with a maximum length of 255 characters.
        * **Example:** `comment TINYTEXT`.
    * **MEDIUMTEXT** - Stores variable-length strings with a maximum length of 16,777,215 characters.
        * **Example:** `story MEDIUMTEXT`.
    * **LONGTEXT** - Stores variable-length strings with a maximum length of 4,294,967,295 characters.
        * **Example:** `biography LONGTEXT`.

* **Binary** data types are used to store binary data, such as images or files.
    * **BINARY(n)** - Stores a fixed-length binary string of length n.
        * **Example:** `binary_data BINARY(10)`.
    * **VARBINARY(n)** - Stores binary data in variable-length format with a maximum length of n.
        * **Example:** `image VARBINARY(255)`.
    * **BLOB** - Stores binary large objects with a maximum length of 65,535 bytes.
        * **Example:** `document BLOB`.
    * **TINYBLOB** - Stores binary large objects with a maximum length of 255 bytes.
        * **Example:** `icon TINYBLOB`.
    * **MEDIUMBLOB** - Stores binary large objects with a maximum length of 16,777,215 bytes.
        * **Example:** `video MEDIUMBLOB`.
    * **LONGBLOB** - Stores binary large objects with a maximum length of 4,294,967,295 bytes.
        * **Example:** `backup LONGBLOB`.

* **Additional Data types** include:
    * **JSON** - Stores JSON formatted data. 
        * **Example:** `preferences JSON`.
    
    * **ENUM** - Stores a list of predefined text values.
        * **Example:** `status ENUM('active', 'inactive', 'pending')`.
    * **SET** - Stores a set of predefined text values.
        * **Example:** `roles SET('admin', 'editor', 'user')`.
    * **GEOMETRY** - Stores geometric data.
        * **Example:** `location GEOMETRY`.
    * **POINT** - Stores a single point in 2D space.
        * **Example:** `position POINT`.
    * **LINESTRING** - Stores a line in 2D space.
        * **Example:** `route LINESTRING`.
    * **POLYGON** - Stores a polygon.
        * **Example:** `area POLYGON`.

##### [Back To Context](./README.md)
***
| &copy; TINITIATE.COM |
|----------------------|