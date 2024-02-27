# SQL

[Creating Databases and Tables](SQL_CRUD.md#creating-databases-and-tables) | [Tables](SQL_CRUD.md#Tables) | [Inserting Data](SQL_CRUD.md#inserting-data) | [Working with NULL](SQL_CRUD.md#working-with-null) | [CRUD Basics](SQL_CRUD.md#crud-basics)
 
## **Creating Databases and Tables**

Local databases are stored where MySQL is installed. MySQL stores databases in a data directory, which contains subdirectories for each individual database. The default location of the data directory varies depending on the operating system. Here are some common default paths:

Windows: C:\ProgramData\MySQL\MySQL Server [version]\data

macOS: /usr/local/mysql/data/

Linux (Ubuntu): /var/lib/mysql/

### **Show Databases**

The command ``` show databases; ``` lists all the databases on the MySQL server.

### **Create a Database**

The command ``` CREATE DATABASE [database name]; ``` creates a new database.

### **Delete a Database**

The command ``` DROP DATABASE [database name]; ``` deletes a database.

### **Using a Database**

using a database is not the same as selecting a database. 

The difference is that using a database **tells MySQL which database you want to work with for the current session**. Selecting a database is used to switch between databases.

The command ``` USE [database name]; ``` selects a database to use.

### **Selecting a Database**

The command ``` SELECT DATABASE(); ``` shows the currently selected database.

## **Tables**

A table is a collection of related data held in a structured format within a database. It consists of columns and rows. It can be visualized as a spreadsheet.

This is the metamodel of Facebook and shows how tables interacts with each other

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/5c260ba7-3ff3-4a7f-8280-9045b90e808d)

### **Creating Tables**

``` CREATE TABLE [tablename] ([column name] [data type], [column name] [data type]); ```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/74f3c44a-dd5b-434b-b401-eb48609a8168)

It can be written in multiple lines:

1. CREATE TABLE [tablename](
2. [column name] [data type],
3. [column name] [data type]
4. );

### **Viewing Tables**

1. To visualize if the table was created, use the command: ```SHOW TABLES;``` inside the database.

2. To visualize the format of the table, use the command: ```SHOW COLUMNS FROM [tablename];``` and its the same as ```DESCRIBE [tablename];``` or ```DESC [tablename];```

### **Dropping Tables**

Use this commando very carefully, because it deletes the table and all the data inside it. There is no warning or confirmation.

The command ```DROP TABLE [tablename];``` deletes a table.

### **MySQL Comments**

```--``` is used to comment a single line.

```/* */``` is used to comment multiple lines.

## **Inserting Data**

### **Inserting Data**

The command ```INSERT INTO [tablename] ([column name], [column name]) VALUES ([value], [value]);``` inserts new rows into a table.

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/163b4695-da45-47df-94de-bc880eaf0b12)

It can be written in multiple lines:

1. INSERT INTO [tablename] (
2. [column name],
3. [column name])
4. VALUES(
5. [value],
6. [value]
7. );

### **Viewing the Data**

The command ```SELECT * FROM [tablename];``` shows all the data in a table.

### **Multiple Inserts**

The command ```INSERT INTO [tablename] ([column name], [column name]) VALUES ([value], [value]), ([value], [value]);``` inserts multiple rows into a table.

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/3d587848-12c0-4e9e-ba08-6551f4ee6dd0)

## **Working with NULL**

When DESC function is used, a column named NULL is shown with 'YES'. It means that the column can be empty. 

To insert a NULL value within a table, use the command ```INSERT INTO [tablename] ([column name], [column name]) VALUES ([value], NULL);``` or ```INSERT INTO [tablename] ([column name]) VALUES ([value]);```. 

The last opinion is available when the table has more the one column and the function inserts data in a single column.

### **Blocking NULL Values**

To block NULL values in a column, use the command ```CREATE TABLE [tablename] ([column name] [data type] NOT NULL);```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/65819e5c-c7fd-4a4b-9a07-b599ace75ec7)

### **Quotes**

Quotes within a string can be escaped with a backslash: ```'I\'m a string';``` or ```"I\'m a string";``` or ```'"HaHaHa';```

### **Default Values**

a column can have a default value. This value is used when no value is specified for the column.

To set a default value for a column, use the command ```CREATE TABLE [tablename] ([column name] [data type] DEFAULT [value]);```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/95ea1378-f257-4464-b931-5f175f9032a1)

### **Primary Keys**

A primary key is a column that uniquely identifies each row in a table. It must contain unique values and cannot contain NULL values.

Primary keys cant be NULL
1. 

To set a primary key for a column, use the command ```CREATE TABLE [tablename] ([column name] [data type] PRIMARY KEY);```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/0aeb298b-c4ad-4287-b5bc-faa5e1f7dc71)

the primary key must be inserted in the first column of the table and its specified with the **Insert** command inside Values.

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/e087da9f-5a43-4049-9e0a-cc5417ca377c)

2.

Another way to set a primary key for a column, use the command ```CREATE TABLE [tablename] ([column name] [data type], PRIMARY KEY ([column name]));```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/63e821ae-f48c-4165-92b0-a6a7feaec4b1)

### **Autoincrement**

Primary key will be auto incremented for new data inserted

```CREATE TABLE [tablename] ([column name] [data type] AUTO_INCREMENT);```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/cdbd60c0-00d8-4b2b-81ae-05f126a614e8)

This way the primaty must not be assign in **Insert** command

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/9d96fc7f-7498-4bd7-b4c3-d18a84913358)

## **CRUD Basics**

CRUD stands for Create, Read, Update and Delete

## **Create**

The creating section envolves all the subjects studied above with **CREATE** and **INSERT**.

## **Read**

### **SELECT command**

Reading data from a table uses the **SELECT** command.

``` SELECT * FROM [DATABASE]``` shows all the columns from a table.
``` SELECT [COLUMN NAME] FROM [DATABASE]``` shows the data from a specific column or ``` SELECT [COLUMN NAME], [COLUMN NAME] FROM [DATABASE]``` for multiple columns.

### **WHERE**

**WHERE** command narrows the selection down with a condition. It can be used with multiple commands but it'll be introduced with **SELECT** command.

```SELECT [COLUMN NAME] FROM [DATABASE] WHERE [CONDITION]```;

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/af024ff2-ce8e-4165-b4b6-af9cb98437b8)

It can be used, for example, to return all the rows in a name column that satisfies the condition within another column.

### **Aliases**

Aliases are tools that simplies or substitutes a column name for another one. This is a temporary change just for the output.

```[SELECT] [COLUMN NAME] AS [NEW NAME] FROM [DATABASE]```

## **Update**

### **UPDATE command**

Updating data from a table.

``` UPDATE [DATABASE] SET [COLUMN = REPLACE] WHERE [CONDITION];```
or ``` UPDATE [DATABASE] SET [COLUMN = REPLACE], [COLUMN = REPLACE] WHERE [CONDITION];```

![image](https://github.com/LuizGustavoVTacin/Oficina/assets/121530417/b5b0fe80-791a-44c6-b45b-7dbb70ff4fc7)

### **Warning** 🚫

```UPDATE [DATASET] SET [COLUMN = REPLACE]``` updates all the rows from a table
### **Rule for preventing a error**

Try selecting the data before updated. That rule prevents the update from losing a data that satisfies the WHERE condition but its not the target.

## **Delete**

### **DELETE command**

```DELETE FROM [DATABASE] WHERE [CONDITION];```

### **Warning** 🚫

```DELETE FROM [DATABASE];``` deletes all the rows from a table
