# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

```sql
SET SERVEROUTPUT ON;

DECLARE
    num1 NUMBER := 80;
    num2 NUMBER := 65;
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/
```

**Expected Output:**  
Greater number is: 80

**Output:**

<img width="617" height="287" alt="image" src="https://github.com/user-attachments/assets/1dc58da1-1359-44e9-a673-0ec19d834bde" />

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

'''sql
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 10;
    sum_n NUMBER := 0;
    i NUMBER := 1;
BEGIN
    WHILE i <= n LOOP
        sum_n := sum_n + i;
        i := i + 1;
    END LOOP;
    
    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum_n);
END;
/
'''

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**Output:**
<img width="626" height="285" alt="image" src="https://github.com/user-attachments/assets/b32e7b75-8a59-4cc7-a5aa-ae49568c8edc" />

---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

'''sql
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER;
BEGIN
    DBMS_OUTPUT.PUT('Fibonacci sequence: ' || a || ', ' || b);
    
    FOR i IN 3..n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT(', ' || c);
        a := b;
        b := c;
    END LOOP;
    
    DBMS_OUTPUT.NEW_LINE;
END;
/
'''

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**Output:**

<img width="622" height="285" alt="image" src="https://github.com/user-attachments/assets/1b82ada8-bfe5-4040-9d4a-6778ac0dfb07" />

---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

'''sql
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 1535;
    reversed_num NUMBER := 0;
    temp NUMBER;
    digit NUMBER;
BEGIN
    temp := n;
    
    WHILE temp > 0 LOOP
        digit := MOD(temp, 10);
        reversed_num := (reversed_num * 10) + digit;
        temp := FLOOR(temp / 10);
    END LOOP;
    
    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed_num);
END;
/
'''

**Expected Output:**  
n = 1535  
Reversed number is 5351

**Output:**

<img width="617" height="279" alt="image" src="https://github.com/user-attachments/assets/92c6faba-fe55-40fd-ae01-ed0c9932a209" />

---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

'''sql
SET SERVEROUTPUT ON;

DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
    
    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
'''

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**Output:**

<img width="620" height="279" alt="image" src="https://github.com/user-attachments/assets/4aec54e7-f97d-4d90-b203-8eeb4170b193" />

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.


