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
<img width="1296" height="710" alt="image" src="https://github.com/user-attachments/assets/59f5297f-8521-47d2-a2bb-9c6e8af70422" />


```sql
SELECT p.*
FROM patients p
INNER JOIN test_results t
  ON p.patient_id = t.patient_id
WHERE t.test_name = 'X-Ray'
  AND t.result = 'Normal';
```

**Output:**

<img width="1250" height="261" alt="image" src="https://github.com/user-attachments/assets/e0a98bdd-94ed-4d00-882d-b211b11c3bbe" />


**Question 2**
---
<img width="628" height="361" alt="image" src="https://github.com/user-attachments/assets/b894f383-6ca1-4ff3-a041-6591e2be871f" />


```sql
select p.first_name as patient_name , d.first_name as doctor_name
from doctors d
inner join patients p on d.doctor_id=p.doctor_id
where p.discharge_date not null;
```

**Output:**

<img width="536" height="245" alt="image" src="https://github.com/user-attachments/assets/1038caaf-c8d0-4ce0-95cb-ffef23fcb078" />


**Question 3**
---
<img width="632" height="255" alt="image" src="https://github.com/user-attachments/assets/b2ea82b4-9d8a-46b3-8e5e-b85cdebe4f59" />


```sql
SELECT c.*
FROM customer AS c
LEFT JOIN orders AS o
    ON c.customer_id = o.customer_id
WHERE o.ord_date > '2012-08-17';
```

**Output:**

<img width="951" height="462" alt="image" src="https://github.com/user-attachments/assets/96d9ff69-c5b6-4b43-b72d-5ac8436b5a42" />


**Question 4**
---
<img width="741" height="737" alt="image" src="https://github.com/user-attachments/assets/61d45623-bf54-4a33-b7db-48adf04ce383" />


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
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1355" height="666" alt="image" src="https://github.com/user-attachments/assets/2a0daaf5-de07-469a-98ad-aab6a23ec4d9" />


**Question 5**
---
<img width="587" height="762" alt="image" src="https://github.com/user-attachments/assets/ebcdd21c-4c33-46b9-8443-56bb300a3e98" />


```sql
select o.ord_no ,o.ord_date,o.purch_amt,c.cust_name as "Customer Name" ,c.grade,s.name as Salesman,s.commission
from orders o
left join customer c on o.customer_id = c.customer_id
left join salesman s on o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1057" height="653" alt="image" src="https://github.com/user-attachments/assets/4820890b-4390-4a42-8679-4970213b88ce" />


**Question 6**
---
<img width="635" height="392" alt="image" src="https://github.com/user-attachments/assets/6bd8cbb6-6c8f-43ba-96b1-1f100187e5e8" />


```sql
select p.first_name as patient_name , a.*
from patients p
inner join appointments a on p.patient_id = a.patient_id;
```

**Output:**

<img width="965" height="306" alt="image" src="https://github.com/user-attachments/assets/8e5b6802-a3d5-4f3f-b9a4-16ae2566ed62" />


**Question 7**
---
<img width="632" height="262" alt="image" src="https://github.com/user-attachments/assets/860fa357-0aff-444d-ad0a-6cd34204fb37" />


```sql
select s.name , c.cust_name, c.city, c.grade, c.salesman_id
from salesman s
left join customer c on s.salesman_id = c.salesman_id;
```

**Output:**

<img width="888" height="502" alt="image" src="https://github.com/user-attachments/assets/9ba5c17a-e81e-4f0f-b3c6-4eebb3e1953a" />


**Question 8**
---
<img width="633" height="517" alt="image" src="https://github.com/user-attachments/assets/210ba26b-b56b-4f4a-9343-d3ae01256022" />


```sql
select o.ord_no,o.purch_amt, c.cust_name, c.city
from orders o
join customer c on o.customer_id = c.customer_id
where o.purch_amt between 500 and 2000;
```

**Output:**

<img width="751" height="283" alt="image" src="https://github.com/user-attachments/assets/b6b2ecf5-c0f4-4e9c-9260-cbc9caacb4d3" />


**Question 9**
---
<img width="631" height="505" alt="image" src="https://github.com/user-attachments/assets/17b9c46d-b6cc-4c4b-b9bd-3781e8ffd852" />


```sql
SELECT 
    c.cust_name as "Customer Name", 
    c.city AS city, 
    s.name AS Salesman, 
    s.commission
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY 
    c.cust_name;
```

**Output:**

<img width="752" height="535" alt="image" src="https://github.com/user-attachments/assets/6d68b9dd-1536-4083-a796-959c639735ac" />


**Question 10**
---
<img width="630" height="617" alt="image" src="https://github.com/user-attachments/assets/b31c26b5-fb08-445e-a920-8d9e7716ee69" />


```sql
SELECT 
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt AS "Order Amount"
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
ORDER BY o.ord_date ASC;
```

**Output:**

<img width="845" height="651" alt="image" src="https://github.com/user-attachments/assets/9ad30933-359f-4add-9302-71860597ebff" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
