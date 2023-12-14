# Student List

## Create a new database
Create a new database for this exercise.
```
CREATE DATABASE exercise_student_list
use exercise_student_list
``
        mysql> CREATE DATABASE exercise_student_list;
        Query OK, 1 row affected (0,00 sec)
        
        mysql> USE exercise_student_list;
        Database changed


## Create the student table
Create a table named **students** with the following columns:  
```
id (integer, primary key)  
name (varchar, maximum length 50)  
age (integer)  
grade (float)  
```

> ANSWER
        mysql> CREATE TABLE students(
    -> id INT PRIMARY KEY,
    -> name VARCHAR(50),
    -> age INT,
    -> grade FLOAT
    -> );
Query OK, 0 rows affected (0,03 sec)


## Insert and Modify Data
### 1. Insert Data
Insert these records into the students table with the following data:
```
(1, 'John Doe', 20, 85.5, '123 Main St')
(2, 'Jane Smith', 22, 92.0, '456 Oak Ave')
(3, 'Bob Johnson', 21, 78.5, '789 Pine Rd')
(4, 'Tina Turner', 25, 71.0, '45 Columbia St')
```

> ANSWER

      mysql> ALTER TABLE students
    -> ADD COLUMN address VARCHAR(100);
Query OK, 0 rows affected (0,01 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> INSERT INTO students (id, name, age, grade, address)
    -> VALUES
    ->     (1, 'John Doe', 20, 85.5, '123 Main St'),
    ->     (2, 'Jane Smith', 22, 92.0, '456 Oak Ave'),
    ->     (3, 'Bob Johnson', 21, 78.5, '789 Pine Rd'),
    ->     (4, 'Tina Turner', 25, 71.0, '45 Columbia St');
Query OK, 4 rows affected (0,00 sec)
Records: 4  Duplicates: 0  Warnings: 0


### Update Data
Update the grade of 'Jane Smith' to 95.0.

> ANSWER

mysql> UPDATE students
    -> SET grade = 95.0
    -> WHERE name = 'Jane Smith';
Query OK, 1 row affected (0,01 sec)
Rows matched: 1  Changed: 1  Warnings: 0


### Delete Data
Delete the record of the student with id 3 from the students table.

> ANSWER

mysql> DELETE FROM students
    -> WHERE id = 3;
Query OK, 1 row affected (0,02 sec)


### Select Data
Write a query to retrieve the names and ages of all students.  

> ANSWER

mysql> SELECT name, age
    -> FROM students;
+-------------+------+
| name        | age  |
+-------------+------+
| John Doe    |   20 |
| Jane Smith  |   22 |
| Tina Turner |   25 |
+-------------+------+
3 rows in set (0,00 sec)


### Bonus: Select the best students
Write a query to retrieve the names and grade of all students with a grade higher than 80.

> ANSWER

mysql> SELECT name, grade
    -> FROM students
    -> WHERE grade > 80;
+------------+-------+
| name       | grade |
+------------+-------+
| John Doe   |  85.5 |
| Jane Smith |    95 |
+------------+-------+
2 rows in set (0,00 sec)


