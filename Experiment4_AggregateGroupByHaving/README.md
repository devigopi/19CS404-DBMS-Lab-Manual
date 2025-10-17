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
<img width="926" height="590" alt="image" src="https://github.com/user-attachments/assets/ef56c4dc-5dc9-48cf-97d4-093dc57a8aba" />


```sql
SELECT DoctorID,count(*) as TotalPrescriptions
FROM Prescriptions
GROUP BY DoctorID;
```

**Output:**

<img width="671" height="741" alt="image" src="https://github.com/user-attachments/assets/b910eb78-3b5f-4569-8457-e24370f6c107" />


**Question 2**
---
<img width="922" height="387" alt="image" src="https://github.com/user-attachments/assets/0d15da88-9daf-4db5-9865-472695eda95a" />


```sql
SELECT Diagnosis,count(*) as DiagnosisCount
FROM MedicalRecords
GROUP BY Diagnosis
ORDER BY DiagnosisCount DESC
LIMIT 1;
```

**Output:**

<img width="782" height="337" alt="image" src="https://github.com/user-attachments/assets/ad7bc3ee-d03b-40a2-bf54-4bba53af0e09" />


**Question 3**
---
<img width="782" height="435" alt="image" src="https://github.com/user-attachments/assets/a78966e8-abbc-4f3a-8b5f-144ae4cfa95d" />


```sql
SELECT name,max(income)
FROM employee
WHERE city='California'
```

**Output:**

<img width="647" height="357" alt="image" src="https://github.com/user-attachments/assets/2f1f04e1-7c0b-41be-bb8c-6c70ea22f71b" />


**Question 4**
---
<img width="1212" height="410" alt="image" src="https://github.com/user-attachments/assets/69d4b700-2c10-4a59-8a83-4aff2a88396f" />


```sql
SELECT 
    SUBSTRING(Email,INSTR(Email, '@') + 1) AS EmailDomain, 
    COUNT(*) AS TotalPatients
FROM Patients
GROUP BY EmailDomain;
```

**Output:**

<img width="1237" height="642" alt="image" src="https://github.com/user-attachments/assets/936bfcbc-deba-48ab-8f7d-920ac074d847" />


**Question 5**
---
<img width="556" height="425" alt="image" src="https://github.com/user-attachments/assets/4a35606a-80cb-4431-8b72-de6fb585abfa" />


```sql
SELECT name,LENGTH(name) as length
FROM customer
order by LENGTH(name) DESC
LIMIT 1;
```

**Output:**

<img width="648" height="342" alt="image" src="https://github.com/user-attachments/assets/f7ffc10e-91ae-4818-b131-d55bc63527b5" />


**Question 6**
---
<img width="927" height="421" alt="image" src="https://github.com/user-attachments/assets/e0649c80-430c-4cb8-8a6d-2a82341b21a6" />


```sql
SELECT MAX(age)-MIN(age) as age_difference
FROM employee
```

**Output:**
<img width="403" height="357" alt="image" src="https://github.com/user-attachments/assets/a2f0ed5f-5064-473b-a1c1-44516a4a6c78" />


**Question 7**
---
<img width="597" height="468" alt="image" src="https://github.com/user-attachments/assets/31445950-f9d7-450c-877c-ef7dd925581f" />



```sql
SELECT min(purch_amt) as MINIMUM
FROM orders
```

**Output:**

<img width="406" height="362" alt="image" src="https://github.com/user-attachments/assets/6d42775c-b66c-422e-90bf-a8a1c48243f4" />



**Question 8**
---
<img width="1227" height="480" alt="image" src="https://github.com/user-attachments/assets/1c57b426-6d56-4246-9ed9-f7b755b3bb36" />



```sql
-- Paste your SQL code below for Question 8
```

**Output:**

![Output8](output.png)

**Question 9**
---
<img width="1211" height="435" alt="image" src="https://github.com/user-attachments/assets/3acaa91e-e4a3-493f-a89b-223794dde884" />


```sql
SELECT age,AVG(income) 
FROM employee  
GROUP BY age
HAVING AVG(income) BETWEEN 300000 and 500000;
```

**Output:**
<img width="575" height="385" alt="image" src="https://github.com/user-attachments/assets/35eea8eb-e1eb-447f-9656-cd251a943140" />


**Question 10**
---
<img width="1223" height="451" alt="image" src="https://github.com/user-attachments/assets/304010d0-453e-4cb5-bcbb-e9c0c11f11e5" />


```sql
SELECT category_id,COUNT(*) as COUNT
FROM products
WHERE category_id>2
GROUP BY category_id;
```

**Output:**

<img width="603" height="361" alt="image" src="https://github.com/user-attachments/assets/1a3f613b-8c9d-46ab-8068-4ee77af5c57c" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
