[String Functions](Aggregate_Refine_Strings.md#String-Functions) | [Refining Selections](Aggregate_Refine_Strings.md#refining-selections) | [Aggregate Functions](Aggregate_Refine_Strings.md#aggregate-functions)

## **String Functions**

All the String Functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/string-functions.html)

String Function | Description | Example
:---: | :---: | :---:
**CONCAT** | Concatenates two or more strings into one. | ```SELECT CONCAT([COLUMN NAME], [COLUMN NAME]) FROM [DATABASE];```
**CONCAT_WS** | Concatenates two or more strings into one with a separator. | ```SELECT CONCAT_WS('[SEPARATOR]', [COLUMN NAME], [COLUMN NAME]) FROM [DATABASE];```
**SUBSTRING** | Returns a part of a string. | ```SELECT SUBSTRING([COLUMN NAME], [START], [LENGTH]) FROM [DATABASE];```
**REPLACE** | Replaces a string with another string. | ```SELECT REPLACE([COLUMN NAME], '[STRING TO REPLACE]', '[STRING TO REPLACE WITH]') FROM [DATABASE];```
**REVERSE** | Reverses a string. | ```SELECT REVERSE([COLUMN NAME]) FROM [DATABASE];```
**CHAR_LENGTH** | Returns the length of a string. | ```SELECT CHAR_LENGTH([COLUMN NAME]) FROM [DATABASE];```
**LOWER** | Converts a string to lowercase. | ```SELECT LOWER([COLUMN NAME]) FROM [DATABASE];```
**UPPER** | Converts a string to uppercase. | ```SELECT UPPER([COLUMN NAME]) FROM [DATABASE];```
**INSERT** | Inserts a string into another string. | ```SELECT INSERT([COLUMN NAME], [START], [LENGTH], '[STRING TO INSERT]') FROM [DATABASE];```
**LEFT** | Returns a specified number of characters from the left of a string. | ```SELECT LEFT([COLUMN NAME], [LENGTH]) FROM [DATABASE];```
**RIGHT** | Returns a specified number of characters from the right of a string. | ```SELECT RIGHT([COLUMN NAME], [LENGTH]) FROM [DATABASE];```
**REPEAT** | Repeats a string a specified number of times. | ```SELECT REPEAT([COLUMN NAME], [NUMBER OF TIMES]) FROM [DATABASE];```
**TRIM** | Removes leading and trailing spaces from a string. | ```SELECT TRIM([COLUMN NAME]) FROM [DATABASE];```



### **SUBSTRING**

* If the length is not specified, the function returns the rest of the string. 

* If the start is not specified, the function returns the string from the start. 

* If both are not specified, the function returns the string.

* If the start is negative, the function returns the string from the end.

* If the length is negative, the function returns the string from the start to the length.

* If both are negative, the function returns the string from the end to the length.

* If the start is greater than the length, the function returns an empty string.

## **Refining Selections**

Refiner Function | Description | Example
:---: | :---: | :---:
**DISTINCT** | Removes duplicate values from a selection. | ```SELECT DISTINCT [COLUMN NAME] FROM [DATABASE];```
**ORDER BY** | Sorts the result set in ascending or descending order. | ```SELECT [COLUMN NAME] FROM [DATABASE] ORDER BY [COLUMN NAME];```
**LIMIT** | Limits the number of rows returned by a query. | ```SELECT [COLUMN NAME] FROM [DATABASE] LIMIT [NUMBER OF ROWS];```
**LIKE** | Selects data based on pattern matching. | ```SELECT [COLUMN NAME] FROM [DATABASE] WHERE [COLUMN NAME] LIKE '[PATTERN]';```


### **DISTINCT**

* If the ORDER BY clause is missing, the result set will be sorted in ascending order by default.

* If the ORDER BY clause is specified with DESC, the result set will be sorted in descending order.

* If the ORDER BY clause is specified with ASC, the result set will be sorted in ascending order.

### **LIMIT**

* If the LIMIT clause is specified with one number, it returns the first number of rows.

* If the LIMIT clause is specified with two numbers, the first number specifies the offset of the first row to return, the second number specifies the maximum number of rows to return.

### **LIKE**

* The percent sign (%) wildcard matches any string of zero or more characters.

* The underscore (_) wildcard matches any single character.

* The percent sign (%) and underscore (_) wildcards can be used in combinations!

## **Aggregate Functions**

All the Aggregate Functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/aggregate-functions.html)

Aggregate Function | Description | Example
:---: | :---: | :---:
**COUNT** | Returns the number of rows in a group. | ```SELECT COUNT([COLUMN NAME]) FROM [DATABASE];```
**COUNT DISTINCT** | Returns the number of unique non-NULL values in a group. | ```SELECT COUNT(DISTINCT [COLUMN NAME]) FROM [DATABASE];```
**GROUP BY** | Groups rows that have the same values into summary rows. | ```SELECT [COLUMN NAME], [AGGREGATE FUNCTION] FROM [DATABASE] GROUP BY [COLUMN NAME];```
**MIN** | Returns the minimum value in a column. | ```SELECT MIN([COLUMN NAME]) FROM [DATABASE];```
**MAX** | Returns the maximum value in a column. | ```SELECT MAX([COLUMN NAME]) FROM [DATABASE];```
**SUM** | Returns the sum of all values in a column. | ```SELECT SUM([COLUMN NAME]) FROM [DATABASE];```
**AVG** | Returns the average value in a column. | ```SELECT AVG([COLUMN NAME]) FROM [DATABASE];```


### **GROUP BY**

* The GROUP BY clause is used with aggregate functions to summarize data into groups, in which each group has a certain value in the column used in the GROUP BY clause.

* The GROUP BY clause returns one row for each group.

* The GROUP BY clause is often used with aggregate functions such as SUM, AVG, MAX, MIN and COUNT.

* If the GROUP BY clause is omitted, the aggregate function treats all rows of the query result set as a single group.

### **Subqueries**

A subquery is a query nested inside another query such as SELECT, INSERT, UPDATE or DELETE.

```SELECT [COLUMN NAME] FROM [DATABASE] WHERE [COLUMN NAME] = (SELECT [COLUMN NAME] FROM [DATABASE] WHERE [COLUMN NAME] = [CONDITION]);```
