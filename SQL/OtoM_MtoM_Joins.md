
## **One to One Relationships**

One to One Relationships are very rarely used in databases, but they do exist. A One to One Relationship is where one record in a table is related to one and only one record in another table. For example, a person may have only one passport, and a passport is issued to only one person.

In this case, the passport number is the primary key in the passport table, and the passport number is also a foreign key in the person table.

## **One to Many Relationships**

One to Many Relationships are the most common type of relationship in databases. In a One to Many Relationship, one record in a table can be related to one or more records in another table, but a record in the second table can be related to only one record in the first table.

For example, a customer can have many orders, but an order can be placed by only one customer. In this case, the customer ID is the primary key in the customers table, and the customer ID is a foreign key in the orders table.

## **Many to Many Relationships**

Many to Many Relationships are also common in databases. In a Many to Many Relationship, one record in a table can be related to one or more records in another table, and a record in the second table can be related to one or more records in the first table. 

For example, a student can choose many courses, and a course can be chosen by many students. In this case, the student ID and the course ID are both primary keys in their tables, and both are foreign keys in the other table.

## **Joins**

Joins are used to combine rows from two or more tables, based on a related column between them. The relations between tables can be: One to One, One to Many, Many to Many. 

### **Cross Join**

A Cross Join is used when you wish to create combination of every row from two tables. That is, if table A has 3 rows and table B has 4 rows, then a Cross Join will result in 12 rows.

```SELECT * FROM table1, table2;```

or

```SELECT * FROM table1 CROSS JOIN table2;```

### **Inner Join**

An Inner Join is used when you wish to create a result set that contains rows from both tables where the join condition is satisfied. 

```SELECT * FROM table1 JOIN table2 ON table1.column1_name = table2.column1_name;```

or

```SELECT * FROM table1 INNER JOIN table2 ON table1.column_name = table2.column_name;```

### ** Inner Join with Group By**

```SELECT table1.column_name, table2.column_name FROM table1 INNER JOIN table2 ON table1.column_name = table2.column_name GROUP BY table1.column_name;```

### **Left Join**

A Left Join is used when you wish to create a result set that contains all the rows from the first (left) table, but only the rows that match from the second (right) table. 

```SELECT * FROM table1 LEFT JOIN table2 ON table1.column_name = table2.column_name;```

### **Right Join**

A Right Join is used when you wish to create a result set that contains all the rows from the second (right) table, but only the rows that match from the first (left) table. 

```SELECT * FROM table1 RIGHT JOIN table2 ON table1.column_name = table2.column_name;```

### **On Delete Cascade**

The ON DELETE CASCADE is used to delete all the records of the referenced table when the primary key in the parent table is deleted. The ON DELETE CASCADE ensures that all the records that are dependent on the primary key will also be deleted.

```ALTER TABLE table_name ADD CONSTRAINT constraint_name FOREIGN KEY (column_name) REFERENCES table_name (column_name) ON DELETE CASCADE;```

or declare a column as a foreign key with ON DELETE CASCADE

```CREATE TABLE table_name (column_name data_type REFERENCES table_name (column_name) ON DELETE CASCADE);```