# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

```sql
select s.name as Salesman, c.cust_name, c.city
from salesman s
join customer c
on s.city = c.city;
```

**Output:**

<img width="826" height="498" alt="image" src="https://github.com/user-attachments/assets/726fbf23-d4af-4f13-a316-4c34e56906a1" />

**Question 2**
---
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name"), with an inner join on the "patient_id" column and a condition filtering for test results with the test name 'Blood Pressure'.

```sql
SELECT p.first_name AS patient_name
FROM patients p
INNER JOIN test_results t
    ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';
```

**Output:**

<img width="331" height="264" alt="image" src="https://github.com/user-attachments/assets/c8d69383-f4fc-4bc6-9a54-b5ce05f34e71" />

**Question 3**
---
Write the SQL query that achieves the selection of all columns from the "patients" table (aliased as "p"), with an inner join on the "patient_id" column and a condition filtering for appointments with an appointment date between '2024-02-01' and '2024-02-28'.

```sql
select p.patient_id, p.first_name, p.last_name, p.date_of_birth, p.admission_date, p.discharge_date, a.doctor_id 
from patients p
join appointments a
on p.doctor_id = a.doctor_id
where a.appointment_date between '2024-02-01' and '2024-02-28'
```

**Output:**

<img width="847" height="264" alt="image" src="https://github.com/user-attachments/assets/072129f5-162a-45e5-ab5e-978caa49a8b0" />

**Question 4**
---
Write the SQL query that achieves the selection of all columns from the "nurses" table (aliased as "n") and the "department_name" column from the "departments" table, with an inner join on the "department_id" column.

```sql
select n.nurse_id, n.first_name, n.last_name, n.department_id , d.department_name
from nurses n
join departments d
on n.department_id = d.department_id;
```

**Output:**

<img width="657" height="384" alt="image" src="https://github.com/user-attachments/assets/81084b80-b4ba-498d-a535-085b3a8052f0" />

**Question 5**
---
Write a SQL statement to join the tables salesman, customer and orders so that the same column of each table appears once and only the relational rows are returned. 

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
INNER JOIN customer c 
    ON o.customer_id = c.customer_id
INNER JOIN salesman s 
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="851" height="576" alt="image" src="https://github.com/user-attachments/assets/31c859b7-4ca6-40f9-a27a-a815eee1e1ce" />

**Question 6**
---
From the following tables write a SQL query to display the customer name, customer city, grade, salesman, salesman city. The results should be sorted by ascending customer_id.  

```sql
select c.cust_name, c.city, c.grade, s.name as Salesman, s.city
from customer c
join salesman s
on c.salesman_id = s.salesman_id
order by customer_id
```

**Output:**

<img width="617" height="468" alt="image" src="https://github.com/user-attachments/assets/cdd18af1-b94c-46db-a4a1-1c97b68495f0" />

**Question 7**
---
From the following tables write a SQL query to find salespeople who received commissions of more than 12 percent from the company. Return Customer Name, customer city, Salesman, commission.  

```sql
select c.cust_name as [Customer Name], c.city, s.name as Salesman, s.commission
from customer c
join salesman s
on c.salesman_id = s.salesman_id
where s.commission > 0.12;
```

**Output:**

<img width="531" height="560" alt="image" src="https://github.com/user-attachments/assets/d9433abd-8bf6-44df-beb6-366a0238555a" />

**Question 8**
---
Write the SQL query that achieves the selection of all columns from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column and a condition filtering for customers with the name 'Fabian Johns'.

```sql
select s.salesman_id, s.name, s.city, s.commission
from salesman s
left join customer c
on s.salesman_id = c.salesman_id
where c.cust_name = 'Fabian Johns'
```

**Output:**

<img width="535" height="266" alt="image" src="https://github.com/user-attachments/assets/529e0637-9c7f-42f8-a52e-7f76837b18a4" />

**Question 9**
---
From the following tables write a SQL query to find the salesperson(s) and the customer(s) he represents. Return Customer Name, city, Salesman, commission.

```sql
select c.cust_name as [Customer Name], c.city, s.name as Salesman, s.commission
from customer c
left join salesman s
on c.salesman_id = s.salesman_id
```

**Output:**

<img width="534" height="460" alt="image" src="https://github.com/user-attachments/assets/228bc2b5-e8c6-4a1c-a029-8119e6ec6adc" />

**Question 10**
---
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column and a condition filtering for customers in the city 'New York'.

```sql
SELECT 
    s.name
FROM salesman AS s
LEFT JOIN customer AS c
    ON s.salesman_id = c.salesman_id
WHERE c.city = 'New York';
```

**Output:**

<img width="327" height="266" alt="image" src="https://github.com/user-attachments/assets/66730e8c-3959-49ed-93ee-003b3f5901a3" />


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
