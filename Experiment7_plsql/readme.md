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
```
### Steps:
1.DECLARE – Used to declare variables (num1, num2, greatest).
2.BEGIN...END – The main executable block.
3.IF...ELSE – Compares the two numbers.
4.DBMS_OUTPUT.PUT_LINE – Displays the result on the screen.
```
```
PL/SQL query
DECLARE
    num1 NUMBER := 25;
    num2 NUMBER := 40;
    greatest NUMBER;
BEGIN
    IF num1 > num2 THEN
        greatest := num1;
    ELSE
        greatest := num2;
    END IF;

    DBMS_OUTPUT.PUT_LINE('The greatest number is: ' || greatest);
END;
/
```
**Expected Output:**
The greatest number is: 40

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers
```
### Steps:
1.n – The limit up to which you want to calculate the sum.
2.i – Loop counter starting from 1.
3.sum – Variable to store the running total.
4.The WHILE loop adds numbers from 1 to n.
5.DBMS_OUTPUT.PUT_LINE displays the final result.
```
```
PL/SQL Program
DECLARE
    n NUMBER := 10;       -- You can change this value or use &n for user input
    i NUMBER := 1;
    sum NUMBER := 0;
BEGIN
    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('The sum of first ' || n || ' natural numbers is: ' || sum);
END;
/
```
**Expected Output:**  
The sum of first 10 natural numbers is: 55


---

## 3. Write a PL/SQL program to generate Fibonacci series
```
### Steps:
1.n → number of terms in the Fibonacci series.
2.a, b, and c → variables to hold consecutive Fibonacci numbers.
3.A WHILE loop calculates the next term each time and appends it to the string result.
4.Finally, DBMS_OUTPUT.PUT_LINE prints the series in one line, neatly formatted.
```
```
PL/SQL Program

DECLARE
    n NUMBER := 7;          -- Number of terms to generate
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER := 3;
    result VARCHAR2(1000);
BEGIN
    result := TO_CHAR(a) || ', ' || TO_CHAR(b);  -- start the series with 0, 1

    WHILE i <= n LOOP
        c := a + b;
        result := result || ', ' || TO_CHAR(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence: ' || result);
END;
/

```

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

---

## 4. Write a PL/SQL Program to display the number in Reverse Order
```
### Steps:
1.n → The number to be reversed.
2.rem → Stores the last digit of the number.
3.rev → Accumulates the reversed number.
4.MOD(temp, 10) extracts the last digit, and FLOOR(temp / 10) removes it.
5.The loop continues until all digits are processed.
```
```
PL/SQL Program
DECLARE
    n NUMBER := 1535;      -- Input number
    rev NUMBER := 0;
    rem NUMBER;
    temp NUMBER;
BEGIN
    temp := n;

    WHILE temp > 0 LOOP
        rem := MOD(temp, 10);           -- Get the last digit
        rev := (rev * 10) + rem;        -- Build the reversed number
        temp := FLOOR(temp / 10);       -- Remove the last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || n);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/

```
**Expected Output:**  
n = 1535  
Reversed number is 5351

---

## 5. Write a PL/SQL program to find the largest of three numbers
```
### Steps:
1.a, b, c → store the three numbers to compare.
2.IF–ELSIF–ELSE statements are used to check which number is the largest.
3.DBMS_OUTPUT.PUT_LINE displays the result clearly in the expected format.
```
```  
PL/SQL Program
  DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF (a >= b) AND (a >= c) THEN
        largest := a;
    ELSIF (b >= a) AND (b >= c) THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
/
```

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.




