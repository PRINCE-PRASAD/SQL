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

CREATE DATABASE databasename;

### For Using Existing Database

USE [datbasename];

### For Delete any Database

DROP DATABASE databasename;

### For creating fields in table

example-

CREATE TABLE employee(

e_id int not null,

e_name varchar(20),

e_salary int,

e_age int,

e_gender varchar(20),

e_dept varchar(20),

primary key(e_id),

);

## Inserting the Records

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
4,'sama', 5000, 25, 'female', 'Operations'
);

insert into employee values(
5,'boby', 8000, 21, 'Female', 'Support'
);

insert into employee values(
6,'Anay', 12500, 20, 'Female', 'Analyst'
);

## Show or Select the entire Record of particular fields

SELECT e_name FROM employee;

## Show or Select the entire Record of multiple fields

SELECT e_name, e_salary, e_age FROM employee;

## For Total Record and Fields of Table

SELECT * FROM employee;

## Show or Select the Different Record(values) of particular fields

SELECT DISTINCT e_gender FROM employee;

## For Filter the Record(Values) from the all table

SELECT * FROM employee WHERE e_gender = 'female';
(it will show only female gender)

SELECT * FROM employee WHERE e_salary >10000 ;
(it will show only that table whoese salary more than 10000)

## SELECT/SHOW ONLY IF BOTH CONDITION ARE TRUE (AND)

SELECT * FROM employee WHERE e_gender='Male' AND e_age<30;

SELECT * FROM employee WHERE e_dept='Analyst' AND e_salary>100000;


## SELECT/SHOW IF ANY ONE OF THE CONDITION TRUE (OR)

SELECT * FROM employee WHERE e_dept='Analyst' OR e_dept='Operations';

SELECT * FROM employee WHERE e_salary>100000 OR e_age<30;

## SELECT/SHOW ONLY IF CONDITION ARE TRUE (NOT)

SELECT * FROM employee WHERE NOT e_gender='Female';

SELECT * FROM employee WHERE NOT e_age<30 ;
