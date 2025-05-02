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
![Screenshot 2025-05-02 125927](https://github.com/user-attachments/assets/1ded7da4-c3f6-4c45-9fa0-053d5561334e)


```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);

```

**Output:**

![Screenshot 2025-05-02 130331](https://github.com/user-attachments/assets/2c5ec048-e418-4398-b3ee-e18cb9c53d7f)


**Question 2**
---
![Screenshot 2025-05-02 125936](https://github.com/user-attachments/assets/f1172150-261a-4b7d-9b94-4b3d6c469e79)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;

```

**Output:**

![Screenshot 2025-05-02 130339](https://github.com/user-attachments/assets/8124782a-e5c2-43d0-adf0-ea16de8aa092)


**Question 3**
---
![Screenshot 2025-05-02 125948](https://github.com/user-attachments/assets/0e303c93-c43b-4b03-9d21-7dc8d2982f70)


```sql
SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';

```

**Output:**

![Screenshot 2025-05-02 130345](https://github.com/user-attachments/assets/05018d9a-b8ba-4eae-8ca8-9b7d165c5a27)


**Question 4**
---
![Screenshot 2025-05-02 130000](https://github.com/user-attachments/assets/1a0e59e4-9881-4073-ae68-7756b8c362a1)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;

```

**Output:**

![Screenshot 2025-05-02 130352](https://github.com/user-attachments/assets/cb4a3d7b-7e77-40a7-b57c-0fe2e634afcf)


**Question 5**
---
![Screenshot 2025-05-02 130008](https://github.com/user-attachments/assets/bd557de9-2161-446e-b11c-daf3a568d5d3)


```sql
SELECT 
    ord_no, 
    purch_amt, 
    ord_date, 
    customer_id, 
    orders.salesman_id
FROM 
    orders
JOIN 
    salesman ON orders.salesman_id = salesman.salesman_id
WHERE 
    salesman.city = 'London';

```

**Output:**

![Screenshot 2025-05-02 130359](https://github.com/user-attachments/assets/734732b7-b6cb-4136-b256-18a4fd868ac6)


**Question 6**
---
![Screenshot 2025-05-02 130016](https://github.com/user-attachments/assets/9041a131-ac65-4465-a2e2-4d58e658437f)


```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 1500;

```

**Output:**

![Screenshot 2025-05-02 130405](https://github.com/user-attachments/assets/9163c16b-0e50-45bb-bd97-dfd09a11b607)


**Question 7**
---
![Screenshot 2025-05-02 130024](https://github.com/user-attachments/assets/1f38ba30-1457-469b-b227-796835cbdfa4)


```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);

```

**Output:**

![Screenshot 2025-05-02 130411](https://github.com/user-attachments/assets/ade99f88-3934-4ac2-92e0-2c84cc9414f7)


**Question 8**
---


```sql
SELECT s.salesman_id, s.name
FROM salesman s
JOIN customer c ON s.salesman_id = c.salesman_id
GROUP BY s.salesman_id, s.name
HAVING COUNT(c.customer_id) > 1;

```

**Output:**

![Screenshot 2025-05-02 130417](https://github.com/user-attachments/assets/0d0c8872-428a-4bfb-b11c-f818aa72b9dd)


**Question 9**
---


```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);

```

**Output:**

![Screenshot 2025-05-02 130424](https://github.com/user-attachments/assets/6872554d-9641-4d7b-912b-28d50d70e152)


**Question 10**
---


```sql
SELECT student_name,grade
FROM GRADES
WHERE grade = (
    SELECT MAX(grade)
    FROM GRADES AS g2
    WHERE g2.subject = GRADES.subject
);


```

**Output:**

![Screenshot 2025-05-02 130431](https://github.com/user-attachments/assets/a2ed8118-4bf3-437c-9301-98085ccb062e)



![Screenshot 2025-05-02 130737](https://github.com/user-attachments/assets/4ef97c16-9c4c-4afb-86d4-4c0809581f29)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
