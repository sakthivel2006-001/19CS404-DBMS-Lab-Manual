# Experiment 4: Aggregate Functions, Group By and Having Clause
```
Developed by;
Name : SAKTHIVEL S
Reg No: 212223220090
```

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
![image](https://github.com/user-attachments/assets/b975a4c1-a98d-4751-a2cc-2ae4c371c482)

**Program:**
```sql
SELECT SUM(income) AS total_income
FROM employee
WHERE age>=40;
```

**Output:**
![image](https://github.com/user-attachments/assets/27514f5d-209c-4232-be18-3279f638013a)


**Question 2**
---
![image](https://github.com/user-attachments/assets/7794d866-5e98-4f9a-838d-62d4fb8f4712)

**Program:**
```sql
SELECT COUNT(DISTINCT age) AS COUNT
FROM employee;
```

**Output:**
![image](https://github.com/user-attachments/assets/afff410c-a3e6-4cd1-9880-ddd0c0d2dd5d)


**Question 3**
---
![image](https://github.com/user-attachments/assets/62a2b6bb-397d-4e57-b89a-daa851c23eb0)

**Program:**
```sql
SELECT COUNT(*) AS employees_in_california
FROM employee
WHERE city='California';
```

**Output:**
![image](https://github.com/user-attachments/assets/52895cd7-0aa4-471f-a7d5-8982c09bba36)


**Question 4**
---
![image](https://github.com/user-attachments/assets/0cc3f666-8b34-44a0-80d4-9ed7e9e2410a)

**Program:**
```sql
SELECT 
    SUBSTR(ValidityPeriod,1,4) AS ValidityYear,
    COUNT(PatientID) AS TotalPatients
FROM
    Insurance
GROUP BY
    SUBSTR(ValidityPeriod,1,4)
ORDER BY
    ValidityYear;
```

**Output:**
![image](https://github.com/user-attachments/assets/c14d1284-ce99-44b3-a94f-227af37c9435)


**Question 5**
---
![image](https://github.com/user-attachments/assets/ef31589c-b07f-4c3e-9aee-f181dde5e7b9)

**Program:**
```sqlSELECT
    Diagnosis,
    COUNT(*) AS DiagnosisCount
FROM
    MedicalRecords
GROUP BY
    Diagnosis
ORDER BY
    DiagnosisCount DESC
LIMIT 1;
```

**Output:**
![image](https://github.com/user-attachments/assets/fb42a7e2-0161-46bc-b855-2d29ce43ac95)


**Question 6**
---
![image](https://github.com/user-attachments/assets/009b407d-902d-4b3d-9200-b685bf040e89)

**Program:**
```sql
SELECT
    Frequency,
    COUNT(*) AS TotalPrescriptions
FROM
    Prescriptions
GROUP BY
    Frequency;
```

**Output:**
![image](https://github.com/user-attachments/assets/c25bf64e-07d8-4561-a19a-7652874b266d)


**Question 7**
---
![image](https://github.com/user-attachments/assets/f08afdaa-3a6f-4ae7-be70-62e4368820a3)

**Program:**
```sql
SELECT
    jdate,
    SUM(workhour)
FROM
    employee1
GROUP BY
    jdate
HAVING
    SUM(workhour) > 40;
```

**Output:**
![image](https://github.com/user-attachments/assets/56cd9419-9f03-4a03-9ab1-b515113d6d5f)


**Question 8**
---
![image](https://github.com/user-attachments/assets/5c2b87a0-f548-48e2-b9b1-c42173a857eb)

**Program:**
```sql
SELECT
    jdate,
    MIN(workhour)
FROM
    employee1
GROUP BY
    jdate
HAVING
    MIN(workhour) < 10;
```

**Output:**
![image](https://github.com/user-attachments/assets/7ef79842-e656-472a-9bfb-4d666aa9f6d4)

**Question 9**
---
![image](https://github.com/user-attachments/assets/b6429d44-f346-4578-9c94-a852cd8a0185)

**Program:**
```sql
SELECT
    city,
    AVG(income)
FROM
    employee
GROUP BY
    city
HAVING
    AVG(income) > 500000;
```

**Output:**
![image](https://github.com/user-attachments/assets/9287d6e8-04b6-43cd-92b6-e2cac55bde33)



**Question 10**
---
![image](https://github.com/user-attachments/assets/a40f8506-28a3-421e-a298-8c62c1fe4729)

**Program:**
```sql
SELECT
    address,
    AVG(salary)
FROM
    customer1
GROUP BY
    address
HAVING
    AVG(salary) > 5000;
```

**Output:**
![image](https://github.com/user-attachments/assets/ae2fb4d9-a575-426e-b39e-164865f194b3)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

## Module Completion
![image](https://github.com/user-attachments/assets/087ce1c1-c916-48ad-ab4f-9820f73de427)
