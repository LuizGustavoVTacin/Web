
## **Views Mode**

Using views is documented in MySQL in the [Views](https://dev.mysql.com/doc/refman/8.0/en/views.html) section of the manual.

Views are a way of storing a query in the database, and then using it as a table. This can be useful for security purposes (you can grant access to the view, but not the underlying tables), or to provide a view of data that is more easily understood than the underlying table structure.

Views can be created from a single table, multiple tables, or even other views. They can be used in the same way as a table, and can be queried, updated, inserted into, and deleted from, subject to the permissions that the user has.

Example:

```CREATE VIEW v AS SELECT * FROM t WHERE i > 5;```

### **Updatable Views**

Views can be updatable, meaning that they can be used to update the underlying tables. This is possible if the view contains all columns from a single table, and the columns are not derived (such as through an aggregate function or calculation). The view must also not contain any of the following:

- Aggregate functions
- DISTINCT
- GROUP BY
- HAVING
- UNION or UNION ALL
- Subqueries in the select list

Example:
    
```CREATE VIEW v AS SELECT * FROM t WHERE i > 5;```
```INSERT INTO v VALUES (6, 'test');```

### **Altering Views**

Views can be altered using the ALTER VIEW command. This can be used to change the definition of the view, or to change the permissions on the view.

Example:

```ALTER VIEW v AS SELECT * FROM t ORDER BY Genre;```
```DROP VIEW v;```

### **Having Clause**

The HAVING clause is used to filter the results of an aggregate function in the same way that the WHERE clause filters the results of a SELECT statement. The HAVING clause is applied after the results of the GROUP BY clause have been calculated.

Example:

```SELECT Genre, COUNT(*) FROM films GROUP BY Genre HAVING COUNT(*) > 5;```

### **Rollup**

The ROLLUP modifier can be used to produce subtotals for each group, and a grand total at the end. It is used in the same way as the GROUP BY clause, but with the addition of the WITH ROLLUP modifier.

Example:

```SELECT Genre, COUNT(*) FROM films GROUP BY Genre WITH ROLLUP;```

In this case, the results will include a row for each genre, and a final row with the grand total, being the last row named NULL.

For multiple columns, the results will include a row for each combination of values, and a row for each subtotal. The subtotals will be calculated for each combination of values in the columns, and the grand total will be calculated for all rows.

## **SQL Modes**

SQL Modes are used to control how MySQL behaves in certain situations. They can be set at the server level, the session level, or the connection level.

All the settings are documented in the [SQL Modes](https://dev.mysql.com/doc/refman/8.0/en/sql-mode.html) section of the manual.

### *Viewing SQL Modes**

The current SQL Modes can be viewed using the following command:

```SELECT @@GLOBAL.sql_mode;``` for the server level
```SELECT @@SESSION.sql_mode;``` for the session level

### *Setting SQL Modes*

SQL Modes can be set at the server level, the session level, or the connection level.

```SET GLOBAL sql_mode = 'modes';``` for the server level
```SET SESSION sql_mode = 'modes';``` for the session level

### **Disabling all modes**

To disable all modes, use the following command:

```SET sql_mode = '';```

### **STRICTTRANS TABLE**

This mode controls how MySQL handles invalid or missing values in data that is being inserted or updated. If this mode is enabled, then MySQL will reject any invalid or missing values, and will not perform the insert or update. If this mode is disabled, then MySQL will insert or update the row, and will insert a default value for any missing values.

To see what are the warnings that are generated, use the following command:

```SHOW WARNINGS;```

### **Modes**

Modes | Description | Default
--- | --- | ---
ONLY_FULL_GROUP_BY | Allows only group by columns in the select list and having clause | Disabled
NO_ZERO_IN_DATE | Disallows dates with zero values | Disabled

## **Window Functions**

All the functions are documented in the [Window Functions](https://dev.mysql.com/doc/refman/8.0/en/window-functions.html) section of the manual.

Window functions are used to perform calculations across a set of rows that are related to the current row. They are similar to aggregate functions, but instead of returning a single value, they return a value for each row.

Window functions are used in conjunction with the OVER clause, which defines the set of rows that the function operates on. The OVER clause can be used to define the window, or it can be omitted, in which case the window is defined as all rows in the result set.

### **OVER Clause**

The OVER clause is used to define the window that the window function operates on. It can be used to define the window, or it can be omitted, in which case the window is defined as all rows in the result set.

Example:

```SELECT Name, Salary, SUM(Salary) OVER() AS Total FROM employees;```

### **Partition By**

The PARTITION BY is used when to devide subgroups of rows into partitions. The window function is then applied to each partition separately.

Example:

```SELECT Name, Salary, SUM(Salary) OVER(PARTITION BY Department) AS Total FROM employees;```

### **Order By**

The ORDER BY clause is used to order the rows within each partition. The window function is then applied to each partition separately.

Example:

```SELECT Name, Salary, SUM(Salary) OVER(PARTITION BY Department ORDER BY Salary) AS Total FROM employees;```

### **Rank**

The RANK function is used to return the rank of each row within the partition. The rank is calculated by ordering the rows within the partition, and then assigning a rank to each row based on its position in the order.

Example:

```SELECT Name, Salary, RANK() OVER(ORDER BY Salary) AS Rank FROM employees;```

When two or more rows have the same value, they are assigned the same rank, and the next row(s) are assigned the next rank. The ranks are consecutive, so there are no gaps in the ranking.

### **Dense Rank**

The DENSE_RANK function is used to return the rank of each row within the partition. The rank is calculated by ordering the rows within the partition, and then assigning a rank to each row based on its position in the order. The difference between RANK and DENSE_RANK is that DENSE_RANK does not skip any ranks if there are gaps in the order.

Example:

```SELECT Name, Salary, DENSE_RANK() OVER(ORDER BY Salary) AS Rank FROM employees;```

### **Row Number**

The ROW_NUMBER function is used to return the row number of each row within the partition. The row number is calculated by ordering the rows within the partition, and then assigning a row number to each row based on its position in the order.

Example:

```SELECT Name, Salary, ROW_NUMBER() OVER(ORDER BY Salary) AS RowNumber FROM employees;```

### **NTILE**

The NTILE function is used to divide the rows within the partition into a specified number of groups. The number of groups is specified as an integer, and the rows are divided into that number of groups as evenly as possible.

Example:

```SELECT Name, Salary, NTILE(4) OVER(ORDER BY Salary) AS Quartile FROM employees;```

### **First Value**

The FIRST_VALUE function is used to return the value of the first row in the partition. The rows are ordered within the partition, and the value of the first row is returned.

Example:

```SELECT Name, Salary, FIRST_VALUE(Salary) OVER(ORDER BY Salary) AS FirstValue FROM employees;```

### **Lead**

The LEAD function is used to return the value of a row that is a specified number of rows after the current row. The rows are ordered within the partition, and the value of the row that is a specified number of rows after the current row is returned.

Example:

```SELECT Name, Salary, LEAD(Salary, 1) OVER(ORDER BY Salary) AS NextSalary FROM employees;```

### **Lag**

The LAG function is used to return the value of a row that is a specified number of rows before the current row. The rows are ordered within the partition, and the value of the row that is a specified number of rows before the current row is returned.