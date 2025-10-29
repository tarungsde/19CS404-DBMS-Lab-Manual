# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
How many medical records are there for each patient?

```sql
select PatientID, count(*) as TotalRecords
from MedicalRecords
group by PatientID;
```

**Output:**

<img width="465" height="475" alt="image" src="https://github.com/user-attachments/assets/d447ac18-3637-4a4c-9732-423dd6f63a90" />

**Question 2**
---
How many prescriptions were written for each medication?

```sql
select Medication, count(*) as TotalPrescriptions
from Prescriptions
group by Medication;
```

**Output:**

<img width="591" height="550" alt="image" src="https://github.com/user-attachments/assets/ab152436-2666-428c-8af6-5704a409e9e0" />

**Question 3**
---
What is the count of male and female patients?

```sql
select Gender, count(*) as TotalPatients
from Patients
group by Gender;
```

**Output:**

<img width="468" height="232" alt="image" src="https://github.com/user-attachments/assets/8914a9ea-3352-4f7b-b6bf-ecf4b2b7be6b" />

**Question 4**
---
Write a SQL query to find  how many employees work in California?

```sql
select count(*) as employees_in_california 
from employee
where city='California';
```

**Output:**

<img width="447" height="197" alt="image" src="https://github.com/user-attachments/assets/1e3393ca-f549-492f-854f-564286be6e95" />

**Question 5**
---
Write a SQL query to find the difference between the maximum and minimum price of fruits?

```sql
select max(price) - min(price) as price_diff
from fruits;
```

**Output:**

<img width="265" height="187" alt="image" src="https://github.com/user-attachments/assets/1498bd5e-e973-4d19-8e84-1de92544d723" />

**Question 6**
---
Write a SQL query to find the average length of email addresses (in characters):

```sql
select avg(length(email)) as avg_email_length
from customer;
```

**Output:**

<img width="341" height="191" alt="image" src="https://github.com/user-attachments/assets/849c4f10-39c3-4278-aa40-47e9ebdfba08" />

**Question 7**
---
Write a SQL query to find the total amount of fruits with a unit type of 'LB'.

```sql
select sum(inventory) as total
from fruits
where unit = 'LB';
```

**Output:**

<img width="253" height="194" alt="image" src="https://github.com/user-attachments/assets/d78d2eb2-7214-4cc5-86a3-4104d575e08f" />

**Question 8**
---
Which cities (addresses) in the "customer1" table have an average salary lesser than Rs. 15000

```sql
select address, AVG(salary)
from customer1
group by address
having AVG(salary) < 15000;
```

**Output:**

<img width="446" height="428" alt="image" src="https://github.com/user-attachments/assets/94bc2f3f-aa0e-4fbc-922b-4463df67bf9c" />

**Question 9**
---
Write the SQL query that achieves the grouping of data by occupation, calculates the minimum work hours for each occupation, and excludes occupations where the minimum work hour is not greater than 8.

```sql
select occupation, MIN(workhour)
from employee1
group by occupation
having MIN(workhour) > 8;
```

**Output:**

<img width="470" height="326" alt="image" src="https://github.com/user-attachments/assets/99a64a8b-8fd4-47ea-ac36-3192bcfa5b48" />

**Question 10**
---
Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.

```sql
select category_id, min(price) as Price
from products
group by category_id
having Price < 10;
```

**Output:**

<img width="441" height="226" alt="image" src="https://github.com/user-attachments/assets/b07f493c-f6c9-4e3a-9fc2-cf01e0e174f2" />


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
