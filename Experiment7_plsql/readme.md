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

### Program
```sql
DECLARE
    a NUMBER := 10;
    b NUMBER := 20;
BEGIN
    IF a > b THEN
        DBMS_OUTPUT.PUT_LINE('Greatest is: ' || a);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greatest is: ' || b);
    END IF;
END;
```

**Expected Output:**  
Greater number is: 80

**Output:**
![alt text](q1.png)
---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

### Program
```sql
DECLARE
    n NUMBER := 5;
    sum NUMBER := 0;
    i NUMBER;
BEGIN
    FOR i IN 1..n LOOP
        sum := sum + i;
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Sum is: ' || sum);
END;
```

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**Output:**
![alt text](q2.png)
---

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

### Program
```sql
DECLARE
    n NUMBER := 10;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER;
BEGIN
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);
    
    FOR i IN 3..n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
    END LOOP;
END;
```

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**Output:**
![alt text](q3.png)
---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

### Program
```sql
DECLARE
    num NUMBER := 1234;
    rev NUMBER := 0;
    rem NUMBER;
BEGIN
    WHILE num > 0 LOOP
        rem := MOD(num, 10);
        rev := rev * 10 + rem;
        num := TRUNC(num / 10);
    END LOOP;
    DBMS_OUTPUT.PUT_LINE('Reversed number: ' || rev);
END;
```

**Expected Output:**  
n = 1535  
Reversed number is 5351

**Output:**
![alt text](q4.png)
---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

### Program
```sql
DECLARE
    a NUMBER := 10;
    b NUMBER := 25;
    c NUMBER := 15;
BEGIN
    IF a > b AND a > c THEN
        DBMS_OUTPUT.PUT_LINE('Largest is: ' || a);
    ELSIF b > c THEN
        DBMS_OUTPUT.PUT_LINE('Largest is: ' || b);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Largest is: ' || c);
    END IF;
END;
```

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**Output:**
![alt text](q5.png)
---

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
