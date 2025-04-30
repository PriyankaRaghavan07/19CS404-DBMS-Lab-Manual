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

![image](https://github.com/user-attachments/assets/94aa7aaa-7819-47ff-8e4b-b638702edd96)

```sql
select * from CUSTOMERS
where ADDRESS='Delhi' and AGE< '30'
ORDER BY ID
```

**Output:**

![image](https://github.com/user-attachments/assets/5fa71681-1f9f-4f94-9d81-3ce1d5ef9b49)

**Question 2**

![image](https://github.com/user-attachments/assets/6773454a-1a58-42b5-8455-e42c96421bcd)

```sql
SELECT * FROM CUSTOMERS
WHERE ADDRESS='Delhi'
```

**Output:**

![image](https://github.com/user-attachments/assets/e0ad038e-4fc1-4247-8851-7c4b8674ef9d)

**Question 3**

![image](https://github.com/user-attachments/assets/522c987a-e37f-4ebb-8538-b969ba825ee5)

```sql
select * from customer
WHERE city <> (SELECT city FROM customer
                order by id DESC 
                LIMIT 1)
```

**Output:**

![image](https://github.com/user-attachments/assets/0e415e10-c641-4b4b-b091-44939d6c1c0a)

**Question 4**

![image](https://github.com/user-attachments/assets/b1b0dbea-464b-4a14-97a9-349bc03cd883)

```sql
select * from CUSTOMERS
WHERE SALARY<2500
```

**Output:**

![image](https://github.com/user-attachments/assets/14617f90-ee7a-4a3b-891c-61bc3b68f064)

**Question 5**

![image](https://github.com/user-attachments/assets/2b5e1c5d-d8ec-497a-9a89-fbcf0e5773a8)

```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>1500
```

**Output:**

![image](https://github.com/user-attachments/assets/1c879168-8787-465a-b13d-f386f7398de6)

**Question 6**

![image](https://github.com/user-attachments/assets/514a177a-0def-4df9-920c-4aa77dfa3081)

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id FROM orders o
JOIN salesman s 
ON o.salesman_id = s.salesman_id
WHERE s.name = 'Paul Adam'
```

**Output:**

![image](https://github.com/user-attachments/assets/fd4a20da-8ef4-4f5e-bf15-23740b9a6838)

**Question 7**
---
![image](https://github.com/user-attachments/assets/d5002bfa-7373-408a-9a46-8d8745f04c54)

```sql
select o.ord_no,o.purch_amt,o.ord_date,o.salesman_id
from orders o
join salesman s on o.salesman_id=s.salesman_id
where s.commission=(select max(commission) from salesman)
```

**Output:**

![image](https://github.com/user-attachments/assets/1dd8d4cc-716b-4c80-a4b3-fcbab6afbb1b)

**Question 8**

![image](https://github.com/user-attachments/assets/f11f805c-c1dc-4874-82a3-c759978a7ce7)

```sql
select grade, COUNT(*) from customer
where grade> (select avg(grade)from customer where city='New York')
GROUP BY grade
```

**Output:**

![image](https://github.com/user-attachments/assets/18176a1f-7412-4295-bf0c-52c3ef4d1f40)

**Question 9**

![image](https://github.com/user-attachments/assets/339ba002-2593-4408-8644-f9488629f912)

```sql
SELECT * FROM CUSTOMERS
WHERE SALARY>4500
```

**Output:**

![image](https://github.com/user-attachments/assets/78db2f5e-e642-4ba8-8747-72348d7e18f0)

**Question 10**

![image](https://github.com/user-attachments/assets/1a31d407-fdeb-46bd-aa40-ee8bb8aaab56)

```sql
select * from CUSTOMERS
WHERE AGE<30
```

**Output:**

![image](https://github.com/user-attachments/assets/3c11f4d6-a284-458c-b9e4-65a74fefe062)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
