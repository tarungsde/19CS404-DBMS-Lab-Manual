# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.

```sql
create table Bonuses (
    BonusID integer primary key,
    EmployeeID integer,
    BonusAmount real check (BonusAmount > 0),
    BonusDate date,
    Reason text not null,
    constraint fk_Employees
        foreign key (EmployeeID) references Employees(EmployeeID)
);
```

**Output:**

<img width="578" height="167" alt="image" src="https://github.com/user-attachments/assets/79d04a53-126a-4e47-81a8-8a0a139f8590" />

**Question 2**
---
Write an SQL query to add two new columns, first_name and last_name, to the table employee. Both columns should have a data type of varchar(50).

```sql
alter table employee
add column first_name varchar(50);

alter table employee
add column last_name varchar(50); 
```

**Output:**

<img width="559" height="184" alt="image" src="https://github.com/user-attachments/assets/7ac79a29-3089-4b55-85ec-038520230d7c" />

**Question 3**
---
Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER

```sql
create table Orders (
    OrderID INTEGER,
    OrderDate TEXT,
    CustomerID INTEGER
);
```

**Output:**

<img width="517" height="238" alt="image" src="https://github.com/user-attachments/assets/5cb34e03-8ff4-4ed9-9eed-a3a9cd2d2a80" />

**Question 4**
---
Write a SQL query to add birth_date attribute as timestamp (datatype) in the table customer 

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002

```sql
alter table customer add column birth_date timestamp;
```

**Output:**

<img width="735" height="223" alt="image" src="https://github.com/user-attachments/assets/55dfa8a9-bc6d-47db-9f51-1b0248679425" />

**Question 5**
---
Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
DueDate as DATE should be greater than the InvoiceDate.
Amount as REAL should be greater than 0.

```sql
create table Invoices (
    InvoiceID INTEGER primary key,
    InvoiceDate DATE,
    DueDate DATE check (DueDate >InvoiceDate),
    Amount REAL check (Amount > 0) 
);
```

**Output:**

<img width="427" height="160" alt="image" src="https://github.com/user-attachments/assets/41466cdb-b780-4f42-90c6-47e48b2bd48f" />

**Question 6**
---
In the Products table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

ProductID   Name              Category    Price       Stock
----------  ---------------   ----------  ----------  ----------
106         Fitness Tracker   Wearables
107         Laptop            Electronics  999.99      50
108         Wireless Earbuds  Accessories              100

```sql
insert into Products values (106, 'Fitness Tracker', 'Wearables', null, null);

insert into Products values (107, 'Laptop', 'Electronic', 999.99, 50); 

insert into Products values (108, 'Wireless Earbud', 'Accessorie', null, 100); 
```

**Output:**

<img width="513" height="167" alt="image" src="https://github.com/user-attachments/assets/760bc2d6-2778-4061-ab7f-b15dfbb34d5e" />

**Question 7**
---
Insert a new product with ProductID 101, Name Laptop, Category Electronics, Price 1500, and Stock 50 into the Products table.

```sql
insert into Products values (101, 'Laptop', 'Electronics', 1500, 50);
```

**Output:**

<img width="485" height="130" alt="image" src="https://github.com/user-attachments/assets/7c8f5dae-d48a-4328-b619-61a3b34ae783" />

**Question 8**
---
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```sql
create table Shipments (
    ShipmentID INTEGER primary key,
    ShipmentDate DATE,
    SupplierID INTEGER,
    OrderID INTEGER,
    constraint fk_Suppliers foreign key (SupplierID) references Suppliers(SupplierID),
    constraint fk_Orders foreign key (OrderID) references Orders(OrderID)
);
```

**Output:**

<img width="320" height="124" alt="image" src="https://github.com/user-attachments/assets/94d28fda-8b03-42d7-8755-c742224ff91a" />

**Question 9**
---
Insert all employees from Former_employees into Employee

Table attributes are EmployeeID, Name, Department, Salary

```sql
insert into Employee select * from Former_employees;
```

**Output:**

<img width="390" height="166" alt="image" src="https://github.com/user-attachments/assets/e289b393-7088-47fb-a12d-eac4fea1879a" />

**Question 10**
---
Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).

```sql
create table Orders (
    OrderID integer primary key,
    OrderDate date not null,
    CustomerID integer,
    constraint fk_Customers
        foreign key (CustomerID) references Customers(CustomerID)
);
```

**Output:**

<img width="316" height="162" alt="image" src="https://github.com/user-attachments/assets/7c95ed6f-0a03-4337-946e-ed70137da7fd" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
