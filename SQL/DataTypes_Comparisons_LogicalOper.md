[Data Types](DataTypes_Comparisons_LogicalOper.md#data-types) | [Logical Operatores](DataTypes_Comparisons_LogicalOper.md#logical-operators)

## **Data Types**

All the Data Types are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)

Numeric Types | String Types | Date and Time Types
------------ | ------------- | -------------
INT | CHAR | DATE
SMALLINT | VARCHAR | DATETIME
TINYINT | BINARY | TIMESTAMP
MEDIUMINT | VARBINARY | TIME
BIGINT | BLOB | YEAR
DECIMAL | TINYBLOB |
NUMERIC | MEDIUMBLOB |
FLOAT | LONGBLOB |
DOUBLE | TEXT |
BIT | TINYTEXT |
| | MEDIUMTEXT |
| | LONGTEXT |
| | ENUM |

### ** CHAR and VARCHAR**

CHAR and VARCHAR are used to store character string values.

* CHAR is a fixed length string data type, so any remaining space in the field is padded with blanks. CHAR takes up 1 byte per character. The length os a CHAR column can be from 0 to 255.

For example:

``` CREATE TABLE states (Abreviations CHAR(4)```

* VARCHAR is a variable length string data type, so it holds only the characters you assign to it. VARCHAR takes up 1 byte per character, + 2 bytes to hold length information.

### **INT**

Type | Bytes | Minimum Value | Maximum Value | Minimum Value Unsigned | Maximum Value Unsigned
-----|-------|---------------|--------------
TINYINT | 1 | -128 | 127 | 0 | 255
SMALLINT | 2 | -32768 | 32767 | 0 | 65535
MEDIUMINT | 3 | -8388608 | 8388607 | 0 | 16777215
INT | 4 | -2147483648 | 2147483647 | 0 | 4294967295
BIGINT | 8 | -9223372036854775808 | 9223372036854775807 | 0 | 18446744073709551615

Example INT Unsigned:

``` CREATE TABLE states (Population INT UNSIGNED);```

### **DECIMAL**

DECIMAL is used to store exact numeric data values.

``` CREATE TABLE states (Population DECIMAL([Total Number of Digits], [Digits After Decimal]));```

### **FLOAT and DOUBLE**

Choosing the right type for a column can be found on: [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/floating-point-types.html)

Store larger numbers using less space than DECIMAL. But it comes with the cost of precision.

``` CREATE TABLE states (Population FLOAT);```

Data Type | Bytes | Minimum Value | Maximum Value | Precision
----------|-------|---------------|---------------|----------
FLOAT | 4 | -3.402823466E+38 | -1.175494351E-38 | 7 digits
DOUBLE | 8 | -1.7976931348623157E+308 | -2.2250738585072014E-308 | 15-16 digits

The precision column above says what position of a decimal number is guaranteed to be correct.

### **DATE and TIME**

All the Date and Time Types are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-types.html)

Dates is stored in the format YYYY-MM-DD.

Times is stored in the format HH:MM:SS or (HHH:MM:SS).

### **CURDATE, CURTIME and NOW**

All the date and time functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)

CURDATE() returns the current date.

CURTIME() returns the current time.

NOW() returns the current date and time.

Example:

``` SELECT CURDATE(), CURTIME(), NOW();```

``` INSERT INTO states (Name, birthdate, birthtime, birthdt) VALUES ('John', CURDATE(), CURTIME(), NOW());```

### **DATE Functions**

Function | Description | Example
---------|-------------|--------
DAY() | Extracts the day of the month as a number (1-31) | SELECT DAY(birthdate);
MONTH() | Extracts the month as a number (1-12) | SELECT MONTH(birthdate);
YEAR() | Extracts the year as a 4-digit number (YYYY) | SELECT YEAR(birthdate);
DAYOFWEEK() | Extracts the weekday as a number (1-7) | SELECT DAYOFWEEK(birthdate);
DAYOFMONTH() | Extracts the day of the month as a number (1-31) | SELECT DAYOFMONTH(birthdate);
DAYOFYEAR() | Extracts the day of the year as a number (1-366) | SELECT DAYOFYEAR(birthdate);
WEEK() | Extracts the week number (0-53) | SELECT WEEK(birthdate);
MONTHNAME() | Extracts the month name | SELECT MONTHNAME(birthdate);
DAYNAME() | Extracts the weekday name | SELECT DAYNAME(birthdate);

### **TIME Functions**

Function | Description | Example
---------|-------------|--------
HOUR() | Extracts the hour | SELECT HOUR(birthtime);
MINUTE() | Extracts the minute | SELECT MINUTE(birthtime);
SECOND() | Extracts the second | SELECT SECOND(birthtime);
DATE() | Extracts the date | SELECT DATE(birthdt);
TIME() | Extracts the time | SELECT TIME(birthdt);

### **Formatting Dates and Times**

* DATE_FORMAT() function formats a date as specified.

The documentation can be found in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html#function_date-format)

Example:

``` SELECT DATE_FORMAT(birthdate, '%m/%d/%Y') FROM states;```

### **DATE MATH**

All the date and time functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)

Function | Description | Example
---------|-------------|--------
DATE_ADD() | Adds a time/date interval to a date and then returns the date | SELECT DATE_ADD(birthdate, INTERVAL 1 YEAR) FROM states;
DATE_SUB() | Subtracts a time/date interval from a date and then returns the date | SELECT DATE_SUB(birthdate, INTERVAL 1 YEAR) FROM states;
DATEDIFF() | Returns the number of days between two dates | SELECT DATEDIFF(NOW(), birthdate) FROM states;

### **TIMESTAMP**

TIMESTAMP is used for values that contain both date and time parts.

TIMESTAMP has a range from '1970-01-01 00:00:01' UTC to '2038-01-19 03:14:07' UTC.

### **TIMESTAMP Functions**

All the timestamps functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/date-and-time-functions.html)

Function | Description | Example
---------|-------------|--------
NOW() | Returns the current date and time | SELECT NOW();
UNIX_TIMESTAMP() | Returns a Unix timestamp | SELECT UNIX_TIMESTAMP();
FROM_UNIXTIME() | Formats a Unix timestamp as a date | SELECT FROM_UNIXTIME(UNIX_TIMESTAMP());
TIMESTAMPDIFF() | Returns the difference between two timestamps | SELECT TIMESTAMPDIFF(SECOND, birthdt, NOW()) FROM states;

## **Logical Operators**

Logical Operatos | Description | Example
-----------------|------------|--------
NOT EQUAL | != | SELECT * FROM states WHERE name != 'California';
NOT | NOT | SELECT * FROM states WHERE name NOT LIKE 'C%';
GREATER THAN | > | SELECT * FROM states WHERE population > 1000000;
LESS THAN | < | SELECT * FROM states WHERE population < 1000000;
AND | AND | SELECT * FROM states WHERE name LIKE 'C%' AND population > 1000000;
OR | OR | SELECT * FROM states WHERE name LIKE 'C%' OR population > 1000000;
BETWEEN | BETWEEN | SELECT * FROM states WHERE population BETWEEN 1000000 AND 2000000;
IN | IN | SELECT * FROM states WHERE name IN ('California', 'Texas', 'New York');
NOT IN | NOT IN | SELECT * FROM states WHERE name NOT IN ('California', 'Texas', 'New York');
IS NULL | IS NULL | SELECT * FROM states WHERE name IS NULL;

### **Comparing Dates**

``` SELECT * FROM states WHERE birthdate > '1980-01-01';```

### **CASE**

CASE is used to create different outputs (usually in the SELECT statement).


``` SELECT name, CASE WHEN population > 1000000 THEN 'Large' ELSE 'Small' END FROM states;```

or

```SELECT name, ```        
```CASE ```         
```WHEN population > 1000000 THEN 'Large' ```  
``` ELSE 'Small'   ```         
```END ```      
```FROM states;```
