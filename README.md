# SQL

## Data

In computing, data is information that has been translated into a form that is efficient for movement or processing. Data can come in the form of text, observations, figures, images, numbers, graphs, or symbols. For example, data might include individual prices, weights, addresses, ages, names, temperatures, dates, or distances.


## Database 

A database is information that is set up for easy access, management and updating. Computer databases typically store aggregations of data records or files that contain information, such as sales transactions, customer data, financials and product information.

## Why we need Database?

Databases support good data access because: Large volumes of data can be stored in one place. Multiple users can read and modify the data at the same time. Databases are searchable and sortable, so the data you need can be found quick and easily.

## DBMS

A database management system (or DBMS) is essentially nothing more than a computerized data-keeping system. Users of the system are given facilities to perform several kinds of operations on such a system for either manipulation of the data in the database or the management of the database structure itself.

## SQL

SQL stands for Structured Query Language. SQL is the standard language for dealing with Relational Databases. SQL can be used to insert, search, update, and delete database records.



### Create Database
```sql
CREATE DATABASE databasename;
```
### For Using Existing Database
```sql
USE [datbasename];
```

### For Delete any Database
```sql
DROP DATABASE databasename;
```
### For creating fields in table

example-
```sql
CREATE TABLE employee(
e_id int not null,
e_name varchar(20),
e_salary int,
e_age int,
e_gender varchar(20),
e_dept varchar(20),
primary key(e_id),
);
```

## Inserting the Records

```sql
insert into employee values(
1,'sam', 95000, 45, 'Male', 'Operations'
);
insert into employee values(
2,'bob', 85000, 35, 'Male', 'Support'
);
insert into employee values(
3,'Ana', 125000, 28, 'Male', 'Analyst'
);
insert into employee values(
4,'sama', 5000, 25, 'Female', 'Operations'
);
insert into employee values(
5,'boby', 8000, 21, 'Female', 'Support'
);
insert into employee values(
6,'Anay', 12500, 20, 'Female', 'Analyst'
);
insert into employee values(
7,'mahashin', 985656, 22, 'Male', 'head'
);
```

## Show or Select the entire Record of particular fields
```sql
SELECT e_name FROM employee;
```

## Show or Select the entire Record of multiple fields
```sql
SELECT e_name, e_salary, e_age FROM employee;
```

## For Total Record and Fields of Table
```sql
SELECT * FROM employee;
```
## Show or Select the Different Record(values) of particular fields
```sql
SELECT DISTINCT e_gender FROM employee;
```
## For Filter the Record(Values) from the all table
```sql
SELECT * FROM employee WHERE e_gender = 'female';
```
(it will show only female gender)
```sql
SELECT * FROM employee WHERE e_salary >10000 ;
```
(it will show only that table whoese salary more than 10000)

## SELECT/SHOW ONLY IF BOTH CONDITION ARE TRUE (AND)
```sql
SELECT * FROM employee WHERE e_gender='Male' AND e_age<30;
SELECT * FROM employee WHERE e_dept='Analyst' AND e_salary>100000;
```

## SELECT/SHOW IF ANY ONE OF THE CONDITION TRUE (OR)
```sql
SELECT * FROM employee WHERE e_dept='Analyst' OR e_dept='Operations';
SELECT * FROM employee WHERE e_salary>100000 OR e_age<30;
```

## SELECT/SHOW ONLY IF CONDITION ARE NOT TRUE (NOT)
```sql
SELECT * FROM employee WHERE NOT e_gender='Female';
SELECT * FROM employee WHERE NOT e_age<30 ;
```

## LIKE Operator used to extract records where a particular pattern is present

Here '%' and ' _ ' are wild card characters '%' Represents Zero, one or Multiple Characters and ' _ ' Represents Single characters.
```sql
SELECT * FROM employee WHERE e_name LIKE 'B%';
SELECT * FROM employee WHERE e_age LIKE '3_';
```

## Between Operator is used to select values with in a Range.
```sql
SELECT * FROM employee WHERE e_salary BETWEEN 50000 AND 100000;
SELECT * FROM employee WHERE e_age BETWEEN 25 AND 30;
```
# FUNCTIONS

## MIN() functions gives you the smallest value From record of particular fields.
```sql
SELECT MIN(e_age) FROM employee;
SELECT MIN(e_salary) FROM employee;
```

## MAX() functions gives you the Biggest value From record of particular fields.
```sql
SELECT MAX(e_age) FROM employee;
SELECT MAX(e_salary) FROM employee;
```

## COUNT() Function returns the number of rows match the specific criteria
```sql
SELECT COUNT(*) FROM employee WHERE e_gender = 'male';
SELECT COUNT(*) FROM employee WHERE e_gender = 'Female';
```

## SUM() function gives the total sum of numeric column
```sql
SELECT SUM(e_salary) FROM employee;
```
## AVG() Function gives the average value of numeric column
```sql
SELECT AVG(e_age) FROM employee;
SELECT AVG(e_salary) FROM employee;
```

# String Function

## LTRIM() Remove the blanks on the left side of the character expression
```sql
SELECT '     SPARTA';
SELECT LTRIM('     SPARTA');
```

## LOWER() Converts all the characters to lower case letters
```sql
SELECT 'THIS IS TOTALLY DONE FOR PRINCE';
SELECT LOWER('THIS IS TOTALLY DONE FOR PRINCE');
```
## UPPER() Converts all the characters to upper case letters
```sql
SELECT 'this is totally done for prince';
SELECT UPPER('this is totally done for prince');
```
## REVERSE() Converts all the characters in the string
```sql
SELECT 'i love coding';
SELECT REVERSE('i love coding');
```
## SUBSTRING() Give a substring from the orignal string
```sql
SELECT 'i love coding';
SELECT SUBSTRING('i love coding',8,13);
--We get the result coding
```


# 'ORDER BY' AND 'TOP' CLAUSE

## ORDER BY is use to sort the data in ascending or descending order by default it is on asending order
```SQL
SELECT * FROM employee ORDER BY e_salary;
-- BY DEFAULT IT IS ASSENDING ORDER 
```
RESULT
```SQL
4	suman   	5000	36	female	Operations
6	Aniy    	12500	23	Male	Analyst
2	bob     	85000	35	Male	Support
5	boby    	95000	25	Female	Support
1	sam     	95000	45	Male	Operations
3	Ana     	125000	28	Male	Analyst
7	mahashin	985656	22	Male	head
```
```SQL
SELECT * FROM employee ORDER BY e_salary DESC;
```

RESULT
```SQL
7	mahashin	985656   22	Male	head
3	Ana         125000   28	Male	Analyst
1	sam	     95000	45	Male	Operations
5	boby	    95000	25	Female  Support
2	bob	     85000	35	Male	Support
6	Aniy	    12500	23	Male	Analyst
4	suman        5000	36	female  Operations
```

## TOP is use to fetch top n(number) records
```sql
SELECT TOP 3 * FROM employee;
```
RESULT
```
1	sam	95000	45	Male	Operations
2	bob	85000	35	Male	Support
3	Ana	125000   28	Male	Analyst
```

EXAMPLE FOR BOTH 'ORDER BY' AND 'TOP' CLAUSE

```SQL
SELECT TOP 3 * FROM employee ORDER BY e_age DESC;
```
RESULT
```SQL
1	sam	95000	45	Male	Operations
4	suman   5000	36	female  Operations
2	bob	85000	35	Male	Support
```

# GROUP BY

## GROUP BY is used to get aggregate result with respect to a group.

```SQL 
SELECT AVG(e_salary), e_gender FROM employee GROUP BY e_gender;
```
RESULT
```SQL
 50000	female
260631	  Male
```
```SQL
SELECT AVG(e_age), e_dept FROM employee GROUP BY e_dept ORDER BY AVG(e_age)DESC;
```
RESULT
```SQL
40	Operations
30	Support
25	Analyst
22	head
```

# HAVING Clause
## HAVING CLAUSE is used in combination with GROUP BY to impose the condition on groups

In this Queary firstly it select the avrage salary and department and then arrange group wise salary more than 10000 
```sql
SELECT e_dept, AVG(e_salary) AS avg_salary FROM employee GROUP BY e_dept HAVING AVG(e_salary)>10000;
```
RESULT 
```SQL
Analyst 	 68750
head    	985656
Operations   50000
Support 	 90000
```

# UPDATE 
## UPDATE is used to modify the existing records in a table.

```sql
UPDATE employee SET e_age=42 WHERE e_name ='sam';
UPDATE employee SET e_dept='tech' WHERE e_gender='female';
UPDATE employee SET e_salary=50000;
SELECT * FROM employee;
```
RESULT
```SQL
1	sam	  50000	42	Male	Operations
2	bob	  50000	35	Male	Support
3	Ana	  50000	28	Male	Analyst
4	suman    50000	36	female  tech
5	boby     50000	25	Female  tech
6	Aniy     50000	23	Male	Analyst
7	mahashin 50000	22	Male	head
```

# DELETE 
## DELETE statement is use to delete existing records in the table

```sql
DELETE FROM employee where e_age=42;
```
# TRUNCATE 
## TRUNCATE Statement deletes all the data inside the table.
```sql
TRUNCATE TABLE employee;
```
It clear only data but structure of table remain constanst.

# JOIN

First create two table

```
-- Table 1
CREATE TABLE department(
d_id int not null,
d_name varchar(20),
d_location varchar(20),
primary key(d_id),
);

insert into department values(
1,'Operations', 'France'
);
insert into department values(
2,'Support', 'Germany'
);
insert into department values(
3,'Analyst', 'Japan'
);
insert into department values(
4,'Head', 'India'
);
insert into department values(
5,'Tester', 'USA'
);
insert into department values(
6,'Security', 'China'
);
insert into department values(
7,'Client', 'Pakistan'
);
```
```
--Table-2
CREATE TABLE employee(
e_id int not null,
e_name varchar(20),
e_salary int,
e_age int,
e_gender varchar(20),
e_dept varchar(20),
primary key(e_id),
);

insert into employee values(
1,'sam', 95000, 45, 'Male', 'Operations'
);
insert into employee values(
2,'bob', 85000, 35, 'Male', 'Support'
);
insert into employee values(
3,'Ana', 125000, 28, 'Male', 'Analyst'
);
insert into employee values(
4,'sama', 5000, 25, 'Female', 'Operations'
);
insert into employee values(
5,'boby', 8000, 21, 'Female', 'Support'
);
insert into employee values(
6,'Anay', 12500, 20, 'Female', 'Analyst'
);
insert into employee values(
7,'mahashin', 985656, 22, 'Male', 'head'
);
insert into employee values(
8,'Prince', 1000000, 35, 'Male', 'CEO'
);
```

## INNER JOIN returns records that have matching values in both the table. It is also known as simple join.


```
SELECT employee.e_name, employee.e_dept, department.d_name, department.d_location
FROM employee
INNER JOIN department 
ON employee.e_dept=department.d_name;
```
RESULT
```
sam	    Operations     Operations 	France
bob	    Support	    Support	    Germany
Ana	    Analyst	    Analyst	    Japan
sama       Operations	 Operations 	France
boby       Support	    Support	    Germany
Anay       Analyst	    Analyst	    Japan
mahashin   head	       Head	       India
```
## LEFT JOIN returns all the records from the left table, and the matched records from the right table.

```
SELECT employee.e_name, employee.e_dept, department.d_name, department.d_location 
FROM employee
LEFT JOIN department 
ON employee.e_dept=department.d_name;
```
RESULT
```
sam	Operations	 Operations 	France
bob	   Support	    Support	Germany
Ana	   Analyst	    Analyst	  Japan
sama Operations	Operations 	France
boby	  Support	    Support	Germany
Anay	  Analyst	    Analyst	  Japan
mahashin 	head	       Head  	India
Prince	    CEO       	NULL	   NULL
```
## RIGHT JOIN return all the records from the right table and matched records from left.

```
SELECT employee.e_name, employee.e_dept, department.d_name, department.d_location
FROM employee
RIGHT JOIN department 
ON employee.e_dept=department.d_name;
```
RESULT
```
sam	Operations	Operations	France
sama   Operations	Operations	France
bob	   Support       Support	Germany
boby      Support	   Support	Germany
Ana	   Analyst       Analyst	Japan
Anay      Analyst	   Analyst	Japan
mahash   	head      	Head	India
NULL     	NULL	    Tester	USA
NULL         NULL	  Security	China
NULL     	NULL    	Client	Pakistan
```
## FULL JOIN all rows from the LEFT table and RIGHT table with NULL values in place where the join condition is not met.

```
SELECT employee.e_name, employee.e_dept, department.d_name, department.d_location
FROM employee
FULL JOIN department 
ON employee.e_dept=department.d_name;
```
RESULT
```
sam	Operations	Operations	France
bob	   Support	   Support	Germany
Ana	   Analyst	   Analyst	Japan
sam    Operations	Operations	France
boby      Support   	Support	Germany
Anay      Analyst   	Analyst	Japan
mahashin     head      	Head	India
Prince        CEO      	NULL	NULL
NULL     	NULL 	   Tester    USA
NULL     	NULL      Security	China
NULL     	NULL        Client	Pakistan
```
