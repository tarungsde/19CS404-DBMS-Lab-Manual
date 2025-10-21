# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
Write a SQL statement to Increase the salary by 500 and email as 'updated' for employees with job ID 'SA_REP' and commission percentage greater than 0.15

```sql
update Employees
set salary = salary + 500
where job_id = 'SA_REP' and commission_pct > 0.15;

update Employees
set email = 'updated'  
where job_id = 'SA_REP' and commission_pct > 0.15; 
```

**Output:**

<img width="481" height="360" alt="image" src="https://github.com/user-attachments/assets/ec701132-bc3d-4196-b743-d1df8e088f8c" />

**Question 2**
---
Decrease the reorder level by 30 percent where the product name contains 'cream' and quantity in stock is higher than reorder level in the products table.

```sql
update products 
set reorder_lvl = reorder_lvl * 0.70
where product_name like '%cream%' and quantity > reorder_lvl;
```

**Output:**

<img width="759" height="339" alt="image" src="https://github.com/user-attachments/assets/415e7c35-8d55-446d-9924-00309e17eebc" />

**Question 3**
---
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

```sql
update Employees 
set hire_date = '2024-01-24'
where department_id = 50;
```

**Output:**

<img width="309" height="169" alt="image" src="https://github.com/user-attachments/assets/07ae77d0-846b-42db-9d54-d31e59b6ccc0" />

**Question 4**
---
Increase the reorder level by 30% for products from 'Food' category having quantity in stock less than 50% of existing reorder level in the products table

```sql
update products
set reorder_lvl = reorder_lvl * 1.30
where category = 'Food' and quantity < reorder_lvl*0.50;
```

**Output:**

<img width="637" height="251" alt="image" src="https://github.com/user-attachments/assets/52faa70d-b71c-4169-aaf2-ffcfce3429a7" />

**Question 5**
---
Write a SQL statement to increase the salary of employees under the department 40, 90 and 110 according to the company rules.

```sql
update Employees 
set salary = round(salary * 1.25, 0)
where department_id = 40;

update Employees 
set salary = round(salary * 1.15, 0)
where department_id = 90; 

update Employees 
set salary = round(salary * 1.10, 0)
where department_id = 110; 
```

**Output:**

<img width="586" height="309" alt="image" src="https://github.com/user-attachments/assets/d6d1ae0d-b8ea-42ce-8997-52dffa6c2c06" />

**Question 6**
---
Write a SQL query to Delete All Doctors whose ID ranges from 2 to 4.

```sql
delete from doctors
where doctor_id > 1 and doctor_id < 5;
```

**Output:**

<img width="419" height="621" alt="image" src="https://github.com/user-attachments/assets/5c47a116-6203-4a12-bae4-75ebb3169406" />

**Question 7**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -
1. 'cust_city' should begin with the letter 'L',

```sql
delete from customer
where cust_city like 'L%';
```

**Output:**

<img width="801" height="547" alt="image" src="https://github.com/user-attachments/assets/b1052f29-d73e-4f09-82ea-66b05009b8e0" />

**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' contains the substring 'Holmes'.

```sql
delete from Customer
where CUST_NAME like '%Holmes%'
```

**Output:**

<img width="802" height="369" alt="image" src="https://github.com/user-attachments/assets/1052ecb2-a04e-4adb-87ca-6398bf1e5c1f" />

**Question 9**
---
Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

```sql
delete from Doctors
where specialization = 'Pediatrics' and first_name = 'Michael';
```

**Output:**

<img width="424" height="249" alt="image" src="https://github.com/user-attachments/assets/260affb4-2d9b-40c2-baac-43c9f97c6dc2" />

**Question 10**
---
Write a SQL query to Delete all Doctors whose Specialization is either 'Pediatrics' or 'Cardiology' and Last Name is Brown.

```sql
delete from Doctors
where (specialization = 'Pediatrics' or specialization = 'Cardiology')
and last_name = 'Brown'; 
```

**Output:**

<img width="421" height="444" alt="image" src="https://github.com/user-attachments/assets/e07b6705-cc6c-43b5-8cc0-dfa2a60dc0c9" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
