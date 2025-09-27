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

<img width="808" height="381" alt="image" src="https://github.com/user-attachments/assets/75e1a743-5b08-4075-ae26-186c47e7aba1" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(202,'Ella King','F','Chemistry',87);
INSERT INTO Student_details(RollNo,Name,Gender,Subject,MARKS)VALUES(203,'James Bond','M','Literature',78)
```

**Output:**

<img width="1271" height="251" alt="image" src="https://github.com/user-attachments/assets/6eb80522-88c3-418c-8295-95661b0bb948" />


**Question 2**

<img width="850" height="378" alt="image" src="https://github.com/user-attachments/assets/cb6a2468-9c4c-4e8d-b4a6-8c874a83d5bc" />


```sql
CREATE TABLE item(
item_id INT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INT NOT NULL,
icom_id TEXT(4),
CONSTRAINT fk_company
    FOREIGN KEY(icom_id)
    REFERENCES Company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
);

```

**Output:**

<img width="1283" height="323" alt="image" src="https://github.com/user-attachments/assets/01ebba4f-c3c6-4b30-b694-c44eb3be5b9a" />


**Question 3**
---
<img width="935" height="302" alt="image" src="https://github.com/user-attachments/assets/62085d2a-0f18-4a93-9ad5-ed978af395ec" />


```sql
ALTER TABLE EMPLOYEES ADD COLUMN Date_of_joining Date;
ALTER TABLE EMPLOYEES RENAME COLUMN job_title TO Designation;

```

**Output:**

<img width="1275" height="351" alt="image" src="https://github.com/user-attachments/assets/e07723b3-038a-4ea0-9479-e17bc6cf40f0" />


**Question 4**
---
<img width="745" height="292" alt="image" src="https://github.com/user-attachments/assets/21253da8-b742-4f67-9d1b-7b793a106d8e" />


```sql
INSERT INTO Customers(CustomerID,Name,Address,Email)
SELECT CustomerID,Name,Address,Email FROM Old_Customers;
```

**Output:**

<img width="1268" height="281" alt="image" src="https://github.com/user-attachments/assets/90cce75e-5624-4c0d-a53a-c53b70e547cd" />


**Question 5**
---
<img width="839" height="343" alt="image" src="https://github.com/user-attachments/assets/25bf6f19-a44b-45f5-806a-80533ac6f58f" />


```sql
CREATE TABLE Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);
```

**Output:**

<img width="1323" height="311" alt="image" src="https://github.com/user-attachments/assets/8d463fd5-6a85-489c-a06d-b7d14695d552" />


**Question 6**
---
<img width="1320" height="194" alt="image" src="https://github.com/user-attachments/assets/77d86e46-fa0a-410c-9990-d821601f6d5b" />


```sql
CREATE TABLE jobs(
job_id INT,
job_title VARCHAR(100)DEFAULT '',
min_salary INT DEFAULT 8000,
max_salary INT DEFAULT NULL);
```

**Output:**

<img width="1325" height="284" alt="image" src="https://github.com/user-attachments/assets/910ed40e-286d-4fb6-b613-024757eab487" />


**Question 7**
---
<img width="858" height="332" alt="image" src="https://github.com/user-attachments/assets/0d326c23-b60a-49e3-8f96-d8d9ec5ccd9d" />


```sql
INSERT INTO Employee(EmployeeID,Name,Position)
VALUES(4,'Emily White','Analyst');
```

**Output:**

<img width="965" height="306" alt="image" src="https://github.com/user-attachments/assets/51419ecb-6a74-4888-9886-0f9116710ba1" />


**Question 8**
---
![WhatsApp Image 2025-09-27 at 09 12 17_abaf5661](https://github.com/user-attachments/assets/b6e75e45-18f1-4a49-a160-ed2530c1c4eb)


```sql
ALTER TABLE customer
ADD discount DECIMAL(5,2);
```

**Output:**

![WhatsApp Image 2025-09-27 at 09 13 54_b23f3c38](https://github.com/user-attachments/assets/2eb2ceab-581f-4307-97d2-6ba5d91af6dd)


**Question 9**
---
<img width="1252" height="393" alt="image" src="https://github.com/user-attachments/assets/9eefadf7-a663-4f86-9afd-7ffb8535e8f2" />


```sql
ALTER TABLE Employee ADD COLUMN department_id INTEGER ;
ALTER TABLE Employee ADD COLUMN manager_id INTEGER DEFAULT NULL ; 
```

**Output:**

<img width="1278" height="286" alt="image" src="https://github.com/user-attachments/assets/8c19c52f-0ab2-40d1-b6ab-0297aff848c7" />


**Question 10**
---
<img width="1316" height="275" alt="image" src="https://github.com/user-attachments/assets/6deda020-18a7-4f8d-a8c3-7b684286bc45" />


```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
BonusAmount REAL CHECK(BonusAmount>0),
BonusDate DATE,
Reason TEXT NOT NULL,
CONSTRAINT fk_employee
    FOREIGN KEY(EmployeeID)
    REFERENCES Employees(EmployeeID))
```

**Output:**

<img width="1334" height="259" alt="image" src="https://github.com/user-attachments/assets/0e28dc12-e91f-40c3-bcc6-75351c8022d9" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
