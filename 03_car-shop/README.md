# Car Shop

## Create a new database
Create a new database for this exercise.
```
CREATE DATABASE exercise_car_shop
use exercise_car_shop
```
mysql> CREATE DATABASE exercise_car_shop;
Query OK, 1 row affected (0,01 sec)

mysql> USE exercise_car_shop;
Database changed


## Setup the table 
Create a table named `cars` for a dealership with the following columns:
   - `car_id` (integer, primary key)
   - `make` (varchar, maximum length 50)
   - `model` (varchar, maximum length 50)
   - `year` (integer)
   - `price` (decimal, 2 decimal places)

> ANSWER
>
> mysql> CREATE TABLE cars(
    -> car_id INT PRIMARY KEY,
    -> make VARCHAR(50),
    -> model VARCHAR(50),
    -> year INT,
    -> price DECIMAL(10, 2)
    -> );
Query OK, 0 rows affected (0,03 sec)


## Add the car data
Insert at least five records into the `cars` table with the following data:
   - (1, 'Toyota', 'Camry', 2022, 25000.00)
   - (2, 'Honda', 'Accord', 2021, 27000.50)
   - (3, 'Ford', 'Mustang', 2023, 35000.75)
   - (4, 'Chevrolet', 'Equinox', 2022, 30000.25)
   - (5, 'Nissan', 'Altima', 2023, 28000.90)
   - (6, 'Tesla', 'Model 3', 2022, 48000.00)
   - (7, 'BMW', 'X5', 2023, 62000.50)
   - (8, 'Mercedes-Benz', 'C-Class', 2022, 55000.75)
   - (9, 'Audi', 'Q7', 2023, 59000.25)
   - (10, 'Lexus', 'RX', 2021, 48000.90)

> ANSWER
>
> mysql> INSERT INTO cars
    -> VALUES
    -> (1, 'Toyota', 'Camry', 2022, 25000.00),
    -> (2, 'Honda', 'Accord', 2021, 27000.50),
    -> (3, 'Ford', 'Mustang', 2023, 35000.75),
    -> (4, 'Chevrolet', 'Equinox', 2022, 30000.25),
    -> (5, 'Nissan', 'Altima', 2023, 28000.90),
    -> (6, 'Tesla', 'Model 3', 2022, 48000.00),
    -> (7, 'BMW', 'X5', 2023, 62000.50),
    -> (8, 'Mercedes-Benz', 'C-Class', 2022, 55000.75),
    -> (9, 'Audi', 'Q7', 2023, 59000.25),
    -> (10, 'Lexus', 'RX', 2021, 48000.90);
Query OK, 10 rows affected (0,01 sec)
Records: 10  Duplicates: 0  Warnings: 0


## Updating records 
### 1. **Update Data**
Update the price of the 'Ford Mustang' to $38000.00.

> ANSWER
>
> mysql> UPDATE cars
    -> SET price = 38000.00
    -> WHERE make = 'Ford'
    -> AND model = 'Mustang';
Query OK, 1 row affected (0,01 sec)
Rows matched: 1  Changed: 1  Warnings: 0


### 2. **Conditional Update**
Increase the price of all cars made in 2022 by 5%.

> ANSWER
>
> mysql> UPDATE cars
    -> SET price = price * 1.05
    -> WHERE year = 2022;
Query OK, 4 rows affected, 2 warnings (0,02 sec)
Rows matched: 4  Changed: 4  Warnings: 2


## Deleting records
### 1. **Delete Data:**
Delete the record of the car with `car_id` 3 from the `cars` table.

> ANSWER
>
> mysql> DELETE FROM cars
    -> WHERE car_id = 3;
Query OK, 1 row affected (0,01 sec)

 
### 1. **Conditional Delete:**
Delete all cars with a price lower than $26000.00.

> ANSWER
>
> mysql> DELETE FROM cars
    -> WHERE price < 26000.00;
Query OK, 0 rows affected (0,00 sec)


## Update and Delete more records
### 7. **Bulk Update:**
Update the prices of all 'Honda' cars to $28000.00.

> ANSWER
>
> mysql> UPDATE cars
    -> SET price = 28000.00
    -> WHERE make = 'Honda';
Query OK, 1 row affected (0,01 sec)
Rows matched: 1  Changed: 1  Warnings: 0


### 8. **Bulk Delete:**
Delete all cars made in 2021.

> ANSWER
> mysql> DELETE FROM cars
    -> WHERE year = 2021;
Query OK, 2 rows affected (0,01 sec)



