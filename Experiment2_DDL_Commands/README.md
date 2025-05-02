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
![Screenshot 2025-05-01 213324](https://github.com/user-attachments/assets/96559919-d9e5-4220-910c-b3ede4233a0b)


```sql
INSERT INTO Employee(EmployeeID, Name, Department, Salary)
SELECT EmployeeID, Name, Department,Salary
FROM Former_employees;

```

**Output:**

![Screenshot 2025-05-01 214546](https://github.com/user-attachments/assets/ff022ec9-cd6c-455d-9c0f-272e23f7debb)


**Question 2**
---
![Screenshot 2025-05-01 213340](https://github.com/user-attachments/assets/614101e5-669f-4c44-8479-04348e67d22c)

```sql
CREATE TABLE Bonuses  (
            BonusID INTEGER PRIMARY KEY,
            EmployeeID INTEGER,
            BonusAmount REAL CHECK (BonusAmount > 0),
            BonusDate DATE,
            Reason TEXT NOT NULL,
            FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID))
```

**Output:**

![Screenshot 2025-05-01 214603](https://github.com/user-attachments/assets/cb865ade-03e0-41d0-9c46-91d2cc768f6a)


**Question 3**
---

![Screenshot 2025-05-01 213347](https://github.com/user-attachments/assets/efcfca1a-a592-4cc3-99f0-d76816b88c74)

```sql
INSERT INTO Employee (EmployeeID,Name,Position,Department,Salary)
VALUES (1,'Sarah Parker','Manager','HR',60000);
```

**Output:**



**Question 4**
---

![Screenshot 2025-05-01 213356](https://github.com/user-attachments/assets/ca7bb4b3-6976-4542-9c94-0e38a972f222)

```sql
CREATE TABLE Departments (DepartmentID INTEGER, DepartmentName TEXT);
```

**Output:**

![Screenshot 2025-05-01 214633](https://github.com/user-attachments/assets/b2c8b7ef-1211-4791-8d76-23e8baa96967)


**Question 5**
---

![Screenshot 2025-05-01 213406](https://github.com/user-attachments/assets/d4ff80a9-cd69-4bf1-91f3-ecfd0a585b16)

```sql
INSERT INTO  Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (202, 'Ella King', 'F', 'Chemistry', 87),
       (203, 'James Bond', 'M', 'Literature', 78);
```

**Output:**

![Screenshot 2025-05-01 214646](https://github.com/user-attachments/assets/8ef9d23b-4778-4e58-8559-62cdcbf91773)


**Question 6**
---
![Screenshot 2025-05-01 213507](https://github.com/user-attachments/assets/624abf68-191e-4d6a-8726-552d17644082)


```sql
CREATE TABLE Orders (
        OrderID INTEGER PRIMARY KEY,
        OrderDate DATE NOT NULL,
        CustomerID INTEGER,
        FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID));
```

**Output:**

![Screenshot 2025-05-01 214659](https://github.com/user-attachments/assets/6f797a71-2287-44dc-af1c-093de0b540fe)


**Question 7**
---

![Screenshot 2025-05-01 213518](https://github.com/user-attachments/assets/19693d8e-60c7-4137-8220-31107ec93e56)

```sql
ALTER TABLE employee ADD COLUMN department_id INTEGER;
ALTER TABLE employee ADD COLUMN manager_id INTEGER DEFAULT NULL;
```

**Output:**

![Screenshot 2025-05-01 214709](https://github.com/user-attachments/assets/10b3dfdb-e3a3-463d-a092-fa6d62bf0b29)


**Question 8**
---
![Screenshot 2025-05-01 213541](https://github.com/user-attachments/assets/b91598fd-b84c-43d3-a802-1c6333de0ac2)


```sql
CREATE TABLE Shipments (
    ShipmentID INTEGER PRIMARY KEY,
    ShipmentDate DATE,
    SupplierID INTEGER,
    OrderID INTEGER,
    FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID));
```

**Output:**

![Screenshot 2025-05-01 214718](https://github.com/user-attachments/assets/6be5a7e6-f20a-49ea-a0ff-ce1e27dd6b86)


**Question 9**
---

![Screenshot 2025-05-01 213547](https://github.com/user-attachments/assets/91e35b62-68de-4027-a52c-0df416c052e1)

```sql
ALTER TABLE Student_details
ADD COLUMN Date_of_birth Date;
```

**Output:**

![Screenshot 2025-05-01 214736](https://github.com/user-attachments/assets/b0d1717c-81b6-47e5-9e14-636d24de13ae)


**Question 10**
---
![Screenshot 2025-05-01 213556](https://github.com/user-attachments/assets/66e5565f-f763-4c19-a24b-497f413f558f)


```sql
CREATE TABLE orders (
        ord_id TEXT NOT NULL CHECK (length(ord_id) = 4),
        item_id TEXT NOT NULL,
        ord_date DATE NOT NULL,
        ord_qty INTEGER,
        cost INTEGER,
        PRIMARY KEY (item_id,ord_date)
        );
```

**Output:**

![Screenshot 2025-05-01 214750](https://github.com/user-attachments/assets/d3bd7f4c-f7b8-45bd-894b-9ef8651c0f88)

![Screenshot 2025-05-01 215155](https://github.com/user-attachments/assets/22835457-2897-453e-a599-d15e3e03eea2)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
