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
![Screenshot 2025-05-01 220205](https://github.com/user-attachments/assets/509a4d30-4e76-45be-9366-028106f44d5c)


```sql
UPDATE employees
SET EMAIL = 'Unavailable';
```

**Output:**

![Screenshot 2025-05-01 221236](https://github.com/user-attachments/assets/f54228f7-23cf-4d98-88d3-d030aafb0253)


**Question 2**
---
![Screenshot 2025-05-01 220219](https://github.com/user-attachments/assets/27f14a01-d055-42fd-b135-e9f608e0beef)


```sql
UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%';
```

**Output:**

![Screenshot 2025-05-01 221301](https://github.com/user-attachments/assets/3f6978d3-892c-4605-9b8f-7d62c03879c3)


**Question 3**
---
![Screenshot 2025-05-01 220228](https://github.com/user-attachments/assets/f46a9bc1-8299-4662-b93a-aa938561b7be)


```sql
UPDATE products
SET reorder_lvl = ROUND(reorder_lvl * 1.3)
WHERE category = 'Food'
    AND quantity < (reorder_lvl * 0.5);
```

**Output:**

![Screenshot 2025-05-01 221319](https://github.com/user-attachments/assets/600b38f4-1900-49cb-b026-ed1ebb435a91)


**Question 4**
---
![Screenshot 2025-05-01 220253](https://github.com/user-attachments/assets/f9c29264-3058-4dec-8bd4-d9ab44336dcf)


```sql
UPDATE products
SET reorder_lvl = ROUND(reorder_lvl * 0.7)
WHERE cost_price > 50
AND quantity < 100;
```

**Output:**

![Screenshot 2025-05-01 221326](https://github.com/user-attachments/assets/976f17c5-f77d-4924-b8ea-365d2bf532ca)


**Question 5**
---
![Screenshot 2025-05-01 220306](https://github.com/user-attachments/assets/3e1769ef-f088-4d5c-afef-8a0e47c270d1)


```sql
UPDATE employees
SET salary = CASE
                    WHEN department_id = 40 THEN ROUND(salary * 1.25)
                    WHEN department_id = 90 THEN ROUND(salary * 1.15)
                    WHEN department_id = 110 THEN ROUND(salary * 1.10)
                    ELSE salary
                    END
WHERE department_id IN (40,90,110);
```

**Output:**

![Screenshot 2025-05-01 221337](https://github.com/user-attachments/assets/c2b2e9d2-ad20-4759-899b-87f34108d10f)


**Question 6**
---
![Screenshot 2025-05-01 220318](https://github.com/user-attachments/assets/2719d592-9949-4ad5-a044-5da4149fe53a)


```sql
DELETE FROM Customer
WHERE LOWER(CUST_NAME) LIKE '%holmes%';
```

**Output:**

![Screenshot 2025-05-01 221438](https://github.com/user-attachments/assets/6e9b2820-8524-44b8-a42b-bfc5f452db7c)


**Question 7**
---
![Screenshot 2025-05-01 220338](https://github.com/user-attachments/assets/888f10ec-298b-4bbc-a8a3-c9deeebae860)


```sql
DELETE FROM Surgeries
WHERE surgery_id = 3;
```

**Output:**

![Screenshot 2025-05-01 221454](https://github.com/user-attachments/assets/19522ba3-5d4e-4c08-80bb-fc3d0d2cf66c)


**Question 8**
---
![Screenshot 2025-05-01 220347](https://github.com/user-attachments/assets/58044fdf-2e9c-440c-b5ec-54c05e6d726b)


```sql
DELETE FROM Doctors
WHERE doctor_id = 1;
```

**Output:**

![Screenshot 2025-05-01 221500](https://github.com/user-attachments/assets/a68bb2dc-2d72-4279-9f88-5a109185cbcf)


**Question 9**
---
![Screenshot 2025-05-01 220939](https://github.com/user-attachments/assets/51efdb64-cc34-49af-b490-5739f4a9d0c8)


```sql
DELETE FROM Doctors
WHERE doctor_id = 1;
```

**Output:**

![Screenshot 2025-05-01 221506](https://github.com/user-attachments/assets/5b37c420-d4cb-45c4-8cf9-464743af9a78)


**Question 10**
---
![Screenshot 2025-05-01 220955](https://github.com/user-attachments/assets/d8b57bac-17de-4ae4-b78e-58fdc3f3b8e9)


```sql
DELETE FROM Surgeries
WHERE surgery_date = '2024-02-28';  
```

**Output:**

![Screenshot 2025-05-01 221517](https://github.com/user-attachments/assets/08960995-2031-4f64-949d-6f66e6be4445)


![Screenshot 2025-05-01 221529](https://github.com/user-attachments/assets/9e345b70-46be-4193-9311-c01b7c1d55bd)



## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
