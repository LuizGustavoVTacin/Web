[Constraints](AlterTable_Constraints.md#constraints) | [ALTER TABLE](AlterTable_Constraints.md#alter-table)

## **Constraints**

### **Unique Constraint**

Unique constraint is used to ensure that all values in a column are different.

``` CREATE TABLE contacts ( name VARCHAR(30) NOT NULL, phone VARCHAR(15) NOT NULL UNIQUE);```

### **Check Constraint**

Check constraint is used to specify a condition on each row when data is inserted into the table.

``` CREATE TABLE contacts ( name VARCHAR(30) NOT NULL, phone VARCHAR(15) NOT NULL, birthdate DATE CHECK (birthdate > '1900-01-01'));```

### **Named Constraints**

Named constraints are used to specify a constraint on a column.

``` CREATE TABLE contacts ( name VARCHAR(30) NOT NULL, phone VARCHAR(15) NOT NULL, birthdate DATE, CONSTRAINT chk_birthdate CHECK (birthdate > '1900-01-01'));```

When the condition is not met, the error message is:

``` ERROR 3819 (HY000): Check constraint 'chk_birthdate' is violated.```

### **Multiple column Constraints**

Multiple column constraints are used to specify a constraint on multiple columns.

``` CREATE TABLE contacts ( name VARCHAR(30) NOT NULL, phone VARCHAR(15) NOT NULL, birthdate DATE, CONSTRAINT chk_name_phone UNIQUE (name, phone));```

## **ALTER TABLE**

All the ALTER TABLE functions are documented in the [MySQL Reference Manual](https://dev.mysql.com/doc/refman/8.0/en/alter-table.html)

### **ALTER TABLE - adding columns**

Alter table is used to add, delete, or modify columns in an existing table.

``` ALTER TABLE [Existing DATABASE name] ADD COLUMN [Column] [Type];```

### **ALTER TABLE - dropping columns**
    
``` ALTER TABLE [Existing DATABASE name] DROP COLUMN [Column];```

### **ALTER TABLE - renaming columns**

``` ALTER TABLE [Existing DATABASE name] RENAME COLUMN [Existing Column] TO [New Column];```
or 

``` RENAME COLUMN [Existing Column] TO [New Column];```

or

``` RENAME TABLE [Existing DATABASE name] TO [New DATABASE name];``` for renaming the table.

### **ALTER TABLE - modifying columns**

``` ALTER TABLE [Existing DATABASE name] MODIFY COLUMN [Existing Column] [New type];```

or 

``` ALTER TABLE [Existing DATABASE name] CHANGE COLUMN [Existing Column] [New Column] [New type];```

### **ALTER TABLE - constraints**

``` ALTER TABLE [Existing DATABASE name] ADD CONSTRAINT [Constraint name] [Constraint type] ([Column]);```
