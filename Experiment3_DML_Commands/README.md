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
<img width="1185" height="622" alt="image" src="https://github.com/user-attachments/assets/af94e44f-1c7f-4667-bb87-5700f3dc4b0f" />


```sql
UPDATE purchases
SET per_unit_price=25, total_price=quantity*25
WHERE purchase_date='2022-08-15' AND product_id=12;
```

**Output:**

<img width="1267" height="255" alt="image" src="https://github.com/user-attachments/assets/09548499-86d2-4cd0-8aaa-c5f35a9ca1d5" />

**Question 2**
---
<img width="887" height="402" alt="image" src="https://github.com/user-attachments/assets/9193dbdb-cfc0-4475-88fe-4c698fb06ba4" />


```sql
UPDATE sales
SET total_sell_price=quantity*sell_price
WHERE product_id=10;
```

**Output:**

<img width="1275" height="320" alt="image" src="https://github.com/user-attachments/assets/d520a31c-f07f-46f9-ba7b-8992590a979a" />


**Question 3**
---
<img width="586" height="303" alt="image" src="https://github.com/user-attachments/assets/1227a3f2-711b-436a-bb39-3e86e117db64" />


```sql
UPDATE suppliers
SET supplier_name=UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%';
```

**Output:**

<img width="1355" height="175" alt="image" src="https://github.com/user-attachments/assets/b3af8d79-7cdc-45c5-b5dd-fd7de3b96c40" />


**Question 4**
---
<img width="593" height="362" alt="image" src="https://github.com/user-attachments/assets/f361538c-effe-43ec-acc3-6c7ae2c5c154" />


```sql
UPDATE PRODUCTS
SET sell_price=ROUND(sell_price*1.10,2)
WHERE supplier_id=6;
```

**Output:**

<img width="1227" height="277" alt="image" src="https://github.com/user-attachments/assets/710f83c6-3ec5-4a27-9d75-bae3d4d01569" />


**Question 5**
---
<img width="665" height="307" alt="image" src="https://github.com/user-attachments/assets/e622b700-6a8c-48f0-9082-de17c309a017" />


```sql
UPDATE Employees
SET salary=8000
WHERE employee_id=105 AND salary<5000;
```

**Output:**

<img width="945" height="132" alt="image" src="https://github.com/user-attachments/assets/f3f79ebe-f01d-449e-8c25-c8ebfc0e484c" />


**Question 6**
---
<img width="728" height="82" alt="image" src="https://github.com/user-attachments/assets/8b31fb8d-c0df-4dc9-8401-648e00e27e61" />


```sql
DELETE FROM Doctors
WHERE specialization='Pediatrics' AND first_name='Michael'
```

**Output:**

<img width="643" height="222" alt="image" src="https://github.com/user-attachments/assets/3e0712ca-e20b-4d98-897e-efe48b6d7072" />


**Question 7**
---
<img width="741" height="256" alt="image" src="https://github.com/user-attachments/assets/52815c71-6ad4-410b-98ff-86a8cf45af68" />


```sql
DELETE FROM Doctors
WHERE (specialization ='Pediatrics' OR specialization='Cardiology') 
AND last_name='Brown';

```

**Output:**

<img width="656" height="520" alt="image" src="https://github.com/user-attachments/assets/a8d8b036-7a2f-4792-be32-31e1208c69c9" />


**Question 8**
---
<img width="795" height="532" alt="image" src="https://github.com/user-attachments/assets/bf89cc2f-5c63-419e-bfdc-6ccbc6df2164" />


```sql
DELETE FROM customer
WHERE AGENT_CODE IN ('A003','A008');
```

**Output:**

<img width="376" height="597" alt="image" src="https://github.com/user-attachments/assets/64ebbf4a-53d9-4144-a350-722301aa3099" />


**Question 9**
---



```sql
SELECT *
FROM employeeposition
WHERE Salary BETWEEN 5000 AND 100000;
```

**Output:**

<img width="552" height="150" alt="image" src="https://github.com/user-attachments/assets/8155fe47-ef6e-4537-ac99-6e28d73ab41f" />


**Question 10**
---
<img width="946" height="307" alt="image" src="https://github.com/user-attachments/assets/190eb007-a96c-4a4e-94cd-5fcb22acf12e" />

```sql
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE grade>100;
```

**Output:**

<img width="920" height="351" alt="image" src="https://github.com/user-attachments/assets/8b320108-cb10-4b83-a72f-c3ec7cc7f499" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
