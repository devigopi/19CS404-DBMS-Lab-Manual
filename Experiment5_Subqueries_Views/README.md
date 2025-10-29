# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1207" height="721" alt="image" src="https://github.com/user-attachments/assets/1ff3faa3-d112-4c8b-abb3-10f7011aaef3" />


```sql
select s.salesman_id ,s.name
from salesman s
JOIN customer c ON s.salesman_id=c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

<img width="882" height="486" alt="image" src="https://github.com/user-attachments/assets/68aa8caf-4592-4e12-bd47-ddc592173587" />


**Question 2**
---
<img width="876" height="743" alt="image" src="https://github.com/user-attachments/assets/51e47b31-4a29-4ca2-9676-c2c25a7773db" />


```sql
select o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
from orders o
JOIN salesman s on o.salesman_id = s.salesman_id
where city = 'London';
```

**Output:**

<img width="1287" height="487" alt="image" src="https://github.com/user-attachments/assets/0c393107-db11-4d71-874c-ee30096d730e" />


**Question 3**
---
<img width="888" height="681" alt="image" src="https://github.com/user-attachments/assets/dafa65a6-2afa-476d-85c4-b084368e0ee0" />

```sql
select g.student_name,g.grade
from grades g
where grade = (
   select min(grade)
   from grades
   where subject=g.subject
);
```

**Output:**

<img width="895" height="523" alt="image" src="https://github.com/user-attachments/assets/ec9528fd-e11e-4fc8-9cd2-83d1a784ffe6" />


**Question 4**
---
<img width="876" height="587" alt="image" src="https://github.com/user-attachments/assets/1b3b5836-304b-441b-943b-91bf9d69b29e" />


```sql
select name,city
from customer
where  city in (
   select city
   from customer
   where id in (3,7)
);
```

**Output:**

<img width="897" height="552" alt="image" src="https://github.com/user-attachments/assets/5eea28fb-3721-46b0-8396-fc9fb541670b" />


**Question 5**
---
<img width="912" height="483" alt="image" src="https://github.com/user-attachments/assets/d7fb89cb-bd2e-4639-b979-0880b2dca3ff" />


```sql
select  *
from Departments
where length(department_name)>(
select avg(length(department_name))
from Departments
);
```

**Output:**

<img width="906" height="482" alt="image" src="https://github.com/user-attachments/assets/edb6a8cc-fd89-4cf4-9443-b135889e52f8" />



**Question 6**
---
<img width="877" height="825" alt="image" src="https://github.com/user-attachments/assets/f9943e34-4a97-4263-af4e-25109069759e" />


```sql
select o.ord_no, o.purch_amt, o.ord_date, o.customer_id ,o.salesman_id
from orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
where s.city = 'New York';
```

**Output:**

<img width="1276" height="580" alt="image" src="https://github.com/user-attachments/assets/8ce7842a-1a98-4ed9-82b8-b90ba24fdc2d" />


**Question 7**
---
<img width="885" height="762" alt="image" src="https://github.com/user-attachments/assets/14b43847-a701-4750-ba13-00607c91229f" />


```sql
select o.ord_no, o.purch_amt, o.ord_date, o.customer_id ,o.salesman_id
from orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
where s.name = 'Paul Adam';
```

**Output:**

<img width="1291" height="488" alt="image" src="https://github.com/user-attachments/assets/252f6989-c8c0-4bb8-84e7-ac5b6ea5c4d8" />


**Question 8**
---
<img width="893" height="613" alt="image" src="https://github.com/user-attachments/assets/0433ba5b-b4a3-423e-8eee-db93eb8337c5" />


```sql
select name
from customer
where phone IN (
    select phone
    from customer
    group by phone
    having count(*)=1
);
```

**Output:**

<img width="897" height="531" alt="image" src="https://github.com/user-attachments/assets/f41f09f9-0823-4ef4-b784-73387f163ba8" />


**Question 9**
---
<img width="902" height="663" alt="image" src="https://github.com/user-attachments/assets/b0486e0d-15e8-4efb-8df4-7e490b61911d" />


```sql
select *
from CUSTOMERS
WHERE ADDRESS = 'Delhi';
```

**Output:**

<img width="1282" height="432" alt="image" src="https://github.com/user-attachments/assets/10afce97-3f11-4808-9da8-fbe5674f3d4f" />


**Question 10**
---
<img width="896" height="757" alt="image" src="https://github.com/user-attachments/assets/20c65c69-4295-494f-998d-23f611cd48d8" />



```sql
select c.customer_id , c.cust_name,c.city,c.grade,c.salesman_id
from customer c
JOIN salesman s ON c.customer_id=(s.salesman_id-2001) and s.name ='Mc Lyon';
```

**Output:**

<img width="1297" height="535" alt="image" src="https://github.com/user-attachments/assets/1241d188-a03d-4c3f-b680-bb8292fb536e" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
