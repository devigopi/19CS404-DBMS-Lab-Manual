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
-- <img width="852" height="355" alt="image" src="https://github.com/user-attachments/assets/2068e2fa-0812-4078-9f5d-9afe521cae19" />


```sql
INSERT INTO Products( ProductID, ProductName, Price,Stock)
SELECT ProductID, ProductName, Price, Stock
FROM Discontinued_products; 
```

**Output:**

<img width="1227" height="303" alt="image" src="https://github.com/user-attachments/assets/be1c75ae-cba5-4e22-8300-d29795ef31f5" />


**Question 2**
---
<img width="1298" height="276" alt="image" src="https://github.com/user-attachments/assets/b8bc00d6-b268-4f90-bacd-2df342ab5ea2" />


```sql
CREATE TABLE contacts(
contact_id INTEGER PRIMARY KEY,
first_name TEXT NOT NULL,
last_name TEXT NOT NULL,
email TEXT,
phone TEXT NOT NULL CHECK (length(phone)>=10)
);
```

**Output:**
<img width="1367" height="163" alt="image" src="https://github.com/user-attachments/assets/aec17f99-1a35-4d04-8f1f-06b586c14eaf" />


**Question 3**
---


```sql
ALTER TABLE customer
ADD COLUMN email VARCHAR(100);
```

**Output:**
<img width="1128" height="176" alt="image" src="https://github.com/user-attachments/assets/e07279d8-6046-4b6f-a78e-cf8f61659166" />



**Question 4**
---
<img width="1023" height="313" alt="image" src="https://github.com/user-attachments/assets/b4e1772d-992b-4299-b01c-ce0ecd81fb8a" />


```sql
ALTER TABLE Student_details
ADD COLUMN MobileNumber NUMBER;
ALTER TABLE Student_details
ADD COLUMN Address VARCHAR(100);
```

**Output:**

<img width="1202" height="252" alt="image" src="https://github.com/user-attachments/assets/4571043e-5587-4274-96a9-6e2af4eca541" />


**Question 5**
---
<img width="843" height="172" alt="image" src="https://github.com/user-attachments/assets/d8c9da17-2ea1-48bc-bd58-f2400184134e" />


```sql
INSERT INTO Products(ProductID, Name, Category, Price, Stock )
VALUES(104,'Tablet','Electronics',100,50)
```

**Output:**

<img width="1128" height="151" alt="image" src="https://github.com/user-attachments/assets/d76bb2be-2dd9-43a8-bbea-c9382675ea39" />


**Question 6**
---
<img width="736" height="311" alt="image" src="https://github.com/user-attachments/assets/f419791a-540c-4efe-a52c-d14108a960cd" />


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT,
CONSTRAINT chk_icom_id_len CHECK (LENGTH(icom_id)=4),
FOREIGN KEY (icom_id) REFERENCES company(com_id) ON UPDATE CASCADE ON DELETE CASCADE
);
```

**Output:**

<img width="1043" height="232" alt="image" src="https://github.com/user-attachments/assets/ef10d27c-14f2-43f3-8c4b-c1319ba60151" />


**Question 7**
---
<img width="897" height="217" alt="image" src="https://github.com/user-attachments/assets/ae21b711-80bd-44e3-854c-1c90756cb77c" />


```sql
CREATE TABLE Shipments(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID), 
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)

);
```

**Output:**

<img width="1183" height="151" alt="image" src="https://github.com/user-attachments/assets/1252026a-ce61-4082-b7b2-1ceb70de0703" />


**Question 8**
---
<img width="642" height="306" alt="image" src="https://github.com/user-attachments/assets/35fdd73d-45a3-4986-9f4c-ca6c52fcd4aa" />


```sql
CREATE TABLE Employees(
EmployeeID INTEGER,
FirstName TEXT,
LastName TEXT,
HireDate DATE
);
```

**Output:**

<img width="1100" height="205" alt="image" src="https://github.com/user-attachments/assets/3773f2f2-c51f-43e4-9a37-01c7dd7540a4" />


**Question 9**
---
<img width="1313" height="182" alt="image" src="https://github.com/user-attachments/assets/82596c3f-870a-480b-bb89-a0817c73d81d" />


```sql
CREATE TABLE jobs(
job_id INTEGER PRIMARY KEY,
job_title VARCHAR(255) DEFAULT ' ',
min_salary INTEGER DEFAULT 8000,
max_salary INTEGER
);
```

**Output:**

<img width="1052" height="162" alt="image" src="https://github.com/user-attachments/assets/d538d06d-d656-42d6-8dc5-bb6b11155523" />


**Question 10**
---
<img width="440" height="238" alt="image" src="https://github.com/user-attachments/assets/f78f6d34-32f3-46dd-a860-966c4a53e083" />


```sql
INSERT INTO Customers (ID,NAME,AGE,ADDRESS,SALARY)
VALUES
    (1,'Ramesh',32,'Ahmedabad',2000),
    (2,'Khilan',25,'Delhi',1500),
    (3,'Kaushik',23,'Kota',2000); 
```

**Output:**

<img width="1223" height="217" alt="image" src="https://github.com/user-attachments/assets/267c88a2-ffb4-4f80-9223-1ae8ac3d8209" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
