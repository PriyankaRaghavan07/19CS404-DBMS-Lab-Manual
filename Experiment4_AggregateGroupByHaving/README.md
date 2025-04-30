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
-- Paste Question 1 here

```sql
-- Paste your SQL code below for Question 1
```

**Question 1**
--
![{C4EAD905-5F81-49D6-BEAD-08963A5DB43E}](https://github.com/user-attachments/assets/f7cf2b25-37df-47ed-990a-88a959aad7bc)

```sql
select Medication,count() as TotalPrescriptions
from Prescriptions
group by Medication
```

**Output:**

![{999353BE-84CC-4020-BA6E-EA016385FAF6}](https://github.com/user-attachments/assets/a9545fb8-8dd7-4b00-9f35-236d1a2adb83)

**Question 2**
---
![{5DD58B65-315D-4DB4-9109-81AA63EF2CB5}](https://github.com/user-attachments/assets/f2e6a7c7-f85d-4cad-8db9-f13bb3f92bf0)

```sql
select DoctorID,count() as TotalPrescriptions from Prescriptions
group by DoctorID
```

**Output:**

![{FA459BF6-05A7-4193-B80E-813A17BC37A8}](https://github.com/user-attachments/assets/7d84fcff-941e-4f70-ac37-b186554589bb)

**Question 3**
![{EEB04734-2C71-471A-9B3A-1E816F522C47}](https://github.com/user-attachments/assets/33560868-4663-4285-9fed-26ed73683330)


```sql
SELECT PatientID,COUNT() as TotalRecords
from MedicalRecords
group by PatientID
```

**Output:**

![{7DA39C03-67A4-4D6A-9E1E-12033232E3BC}](https://github.com/user-attachments/assets/2fb7982d-47a5-4d32-bfa6-d26eead47073)


**Question 4**
---
![{0BF1E2DC-751E-46A5-A5E1-281EB2B62289}](https://github.com/user-attachments/assets/bfb51534-6964-4a2d-9e00-bd8e563ca133)


```sql
select name,length(name) as length from customer
ORDER BY LENGTH(name) DESC
LIMIT 1

```

**Output:**

![{F55D891C-13BC-4A19-918A-E7FC1198BD84}](https://github.com/user-attachments/assets/b3736946-5409-4b97-84cc-6214c8bb1fe0)


**Question 5**
---
![{48B19B28-4975-4601-8A17-4807F6A71D73}](https://github.com/user-attachments/assets/35da9886-25a1-45fa-bfec-b26a0372443a)


```sql
select sum(income) as 'total_income' from employee
where age>=40
```

**Output:**

![{EED6A9DE-B6A8-4AA1-88CD-D0AEE424A1DD}](https://github.com/user-attachments/assets/34d7f6ee-bd6c-4ab6-a2a3-edb6da5e6650)


**Question 6**
![{535B9A25-A992-44B8-95A1-48F871E0F127}](https://github.com/user-attachments/assets/53db6d45-1bbf-42dd-850b-4478873ca6e6)


```sql
select COUNT(DISTINCT(salesman_id)) as 'COUNT' FROM orders
```

**Output:**

![{8ED24307-016F-4CC2-9274-C52518ECF991}](https://github.com/user-attachments/assets/8b4327ed-507b-4622-b661-7caae5f14a81)


**Question 7**
---
![{024D2596-7B12-4155-8102-0B19E8C148DB}](https://github.com/user-attachments/assets/471c2ed3-115c-48d1-935b-f50eba65198f)


```sql
select max(age) - min(age) as 'age_difference' from employee
```

**Output:**

![{75234451-6E7B-4C2E-AFBC-F01C4C92B866}](https://github.com/user-attachments/assets/b95f18f6-5b9b-488b-a16d-d166827598e9)


**Question 8**
---
![{C37A31C9-DB3D-46E9-825D-E4E8F6FCEDA9}](https://github.com/user-attachments/assets/816d8f02-fa5a-4a13-931d-9bf45c9dd957)


```sql
select category_id, sum(price*category_id) as 'Revenue' from products
group by category_id
having Revenue > 25
```

**Output:**

![{1D0D9F97-C574-4D3E-AD9F-95210D4C3012}](https://github.com/user-attachments/assets/612cce80-0dc2-4e6a-9c99-f245bcbd8f37)


**Question 9**
---
![{640C8FAD-AE6D-49F8-B061-9A87510D067D}](https://github.com/user-attachments/assets/71d9668a-276a-4a4f-8639-7d8ce5b2c4d6)


```sql
select PatientID,COUNT(*) AS 'TotalRecords' from MedicalRecords
group by PatientID
HAVING TotalRecords > 3
```

**Output:**

![{36CB33B5-20BC-4B47-A97C-4BAA5319C36B}](https://github.com/user-attachments/assets/0186a549-5974-4a8a-9021-ab5a198b4c6a)


**Question 10**
---
![{6BBD9AC7-4DA6-4C27-8D8D-717B1BFC5E17}](https://github.com/user-attachments/assets/c2205938-7bba-43c0-9de7-dbed18de9ab8)


```sql
select category_id,count(*) as COUNT FROM products
group by category_id
having category_id>2
```

**Output:**

![{20F7198D-1790-4B85-9D27-C42AE4475B11}](https://github.com/user-attachments/assets/8044026c-f4db-43ce-977e-b3d0b7e35172)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
