# 💻 **03 — SQL COMMANDS**

---

## 📌 **1. SQL Kya Hai?**

**SQL** ka full form hai:

> **Structured Query Language**

SQL ek standard language hai jiska use **database ke saath communicate** karne aur data ko create, retrieve, modify aur manage karne ke liye kiya jata hai.

### 🧠 **Simple Hinglish**

SQL ko hum database se baat karne ki language samajh sakte hain.

Jaise hume database se kehna ho:

- 🗃️ Database banao
- 📊 Table banao
- ➕ Data add karo
- 🔍 Data dikhao
- ✏️ Data change karo
- ❌ Data delete karo

To hum **SQL Commands** use karte hain.

---

# 🎯 **2. SQL Commands Kya Hain?**

SQL Commands wo instructions/statements hain jo database par different operations perform karne ke liye use kiye jate hain.

### 📌 Example

```sql
SELECT * FROM Student;
```

Ye command `Student` table ka data display karti hai.

---

# 📚 **3. Types of SQL Commands**

SQL Commands ko mainly following categories mein divide kiya jata hai:

| 🔢 Type | 📖 Full Form | 🎯 Purpose |
|---|---|---|
| **DDL** | Data Definition Language | Database structure define/change karna |
| **DML** | Data Manipulation Language | Data insert/update/delete karna |
| **DQL** | Data Query Language | Data retrieve karna |
| **DCL** | Data Control Language | Permissions/access control |
| **TCL** | Transaction Control Language | Transactions manage karna |

### 🧠 **Easy Trick**

```text
DDL → Structure
DML → Data Manipulation
DQL → Data Query
DCL → Control
TCL → Transaction
```

---

# 🏗️ **4. DDL — Data Definition Language**

**DDL** ka full form hai:

> **Data Definition Language**

DDL commands ka use database ke **structure/schema** ko create, modify aur delete karne ke liye hota hai.

### 📌 Common DDL Commands

| Command | Purpose |
|---|---|
| `CREATE` | New database/table/object create |
| `ALTER` | Existing structure modify |
| `DROP` | Object completely delete |
| `TRUNCATE` | Table ke all rows remove |

---

## 🔹 **CREATE Command**

`CREATE` command ka use new database ya table create karne ke liye hota hai.

### 📌 Database Create

```sql
CREATE DATABASE CollegeDB;
```

### 📌 Table Create

```sql
CREATE TABLE Student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Course VARCHAR(30)
);
```

---

## 🔹 **ALTER Command**

`ALTER` command ka use existing table ke structure mein changes karne ke liye hota hai.

### 📌 New Column Add Karna

```sql
ALTER TABLE Student
ADD Email VARCHAR(100);
```

### 📌 Column Modify Karna

```sql
ALTER TABLE Student
MODIFY Name VARCHAR(100);
```

### 📌 Column Delete Karna

```sql
ALTER TABLE Student
DROP COLUMN Email;
```

---

## 🔹 **DROP Command**

`DROP` command ka use database object ko completely remove karne ke liye hota hai.

### 📌 Table Delete

```sql
DROP TABLE Student;
```

### 📌 Database Delete

```sql
DROP DATABASE CollegeDB;
```

> ⚠️ **Important:** `DROP` object ko completely remove kar sakta hai, isliye carefully use karna chahiye.

---

## 🔹 **TRUNCATE Command**

`TRUNCATE` command table ki **all rows remove** karne ke liye use hoti hai, while table structure remains available.

### 📌 Query

```sql
TRUNCATE TABLE Student;
```

### 🧠 **Important**

```text
TRUNCATE
   ↓
All Rows Remove
   ↓
Table Structure Remains
```

---

# ✏️ **5. DML — Data Manipulation Language**

**DML** ka full form hai:

> **Data Manipulation Language**

DML commands ka use table ke andar stored **data ko manipulate** karne ke liye hota hai.

### 📌 Common DML Commands

| Command | Purpose |
|---|---|
| `INSERT` | Data add |
| `UPDATE` | Existing data change |
| `DELETE` | Data remove |

---

## 🔹 **INSERT Command**

`INSERT` command ka use table mein new records add karne ke liye hota hai.

### 📌 Syntax

```sql
INSERT INTO table_name
(column1, column2)
VALUES
(value1, value2);
```

### 📌 Example

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(101, 'Kajal', 18, 'CSE');
```

### 📌 Multiple Records

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(102, 'Rahul', 19, 'IT'),
(103, 'Priya', 18, 'CSE');
```

---

## 🔹 **UPDATE Command**

`UPDATE` command existing data ko modify/change karne ke liye use hoti hai.

### 📌 Example

```sql
UPDATE Student
SET Age = 19
WHERE Roll_No = 101;
```

### 🧠 **Explanation**

- `UPDATE Student` → Student table ko update karo
- `SET Age = 19` → Age ko 19 karo
- `WHERE Roll_No = 101` → Sirf Roll No 101 wale record par apply karo

> ⚠️ **Important:** `WHERE` condition na lagane par multiple/all rows update ho sakti hain.

---

## 🔹 **DELETE Command**

`DELETE` command table se records remove karne ke liye use hoti hai.

### 📌 Example

```sql
DELETE FROM Student
WHERE Roll_No = 103;
```

Isse Roll No `103` wala record delete hoga.

> ⚠️ **Important:** `WHERE` condition carefully use karein.

---

# 🔍 **6. DQL — Data Query Language**

**DQL** ka full form hai:

> **Data Query Language**

DQL ka use database se **data retrieve/read** karne ke liye kiya jata hai.

### ⭐ Main DQL Command

```text
SELECT
```

---

## 🔹 **SELECT Command**

`SELECT` command ka use table se data retrieve karne ke liye hota hai.

### 📌 All Columns

```sql
SELECT * FROM Student;
```

### 📌 Specific Columns

```sql
SELECT Name, Course
FROM Student;
```

### 📊 **Example Output**

| Name | Course |
|---|---|
| Kajal | CSE |
| Rahul | IT |
| Priya | CSE |

---

## 🔹 **SELECT with WHERE**

Specific condition ke according data retrieve karne ke liye:

```sql
SELECT * FROM Student
WHERE Course = 'CSE';
```

### 🧠 **Meaning**

Sirf un students ka data show hoga jinka course `CSE` hai.

---

# 🔐 **7. DCL — Data Control Language**

**DCL** ka full form hai:

> **Data Control Language**

DCL commands ka use database mein **user permissions aur access control** manage karne ke liye hota hai.

### 📌 Common DCL Commands

| Command | Purpose |
|---|---|
| `GRANT` | Permission dena |
| `REVOKE` | Permission wapas lena |

---

## 🔹 **GRANT Command**

`GRANT` ka use user ko privileges dene ke liye hota hai.

### 📌 Example

```sql
GRANT SELECT
ON CollegeDB.Student
TO 'student'@'localhost';
```

Isse specified user ko `Student` table par `SELECT` privilege diya ja sakta hai.

---

## 🔹 **REVOKE Command**

`REVOKE` ka use previously given privilege ko remove karne ke liye hota hai.

### 📌 Example

```sql
REVOKE SELECT
ON CollegeDB.Student
FROM 'student'@'localhost';
```

---

# 🔄 **8. TCL — Transaction Control Language**

**TCL** ka full form hai:

> **Transaction Control Language**

TCL commands ka use database transactions ko manage karne ke liye hota hai.

### 📌 Common TCL Commands

| Command | Purpose |
|---|---|
| `COMMIT` | Changes permanently save |
| `ROLLBACK` | Uncommitted changes undo |
| `SAVEPOINT` | Transaction mein temporary point create |

---

## 🔹 **COMMIT**

`COMMIT` transaction ke changes ko permanently save karne ke liye use hota hai.

### 📌 Example

```sql
COMMIT;
```

---

## 🔹 **ROLLBACK**

`ROLLBACK` uncommitted changes ko undo karne ke liye use hota hai.

### 📌 Example

```sql
ROLLBACK;
```

> 💡 **Note:** Transaction behavior command aur storage engine/configuration par depend kar sakta hai. MySQL mein transactional tables ke saath `COMMIT` aur `ROLLBACK` commonly use hote hain.

---

## 🔹 **SAVEPOINT**

`SAVEPOINT` transaction ke andar ek point create karta hai jahan tak baad mein rollback kiya ja sakta hai.

### 📌 Example

```sql
SAVEPOINT sp1;
```

### 📌 Rollback to Savepoint

```sql
ROLLBACK TO SAVEPOINT sp1;
```

---

# 🆚 **9. DDL vs DML vs DQL vs DCL vs TCL**

| Feature | DDL | DML | DQL | DCL | TCL |
|---|---|---|---|---|---|
| Full Form | Data Definition Language | Data Manipulation Language | Data Query Language | Data Control Language | Transaction Control Language |
| Main Purpose | Structure | Data manipulation | Data retrieval | Permissions | Transactions |
| Main Commands | CREATE, ALTER, DROP, TRUNCATE | INSERT, UPDATE, DELETE | SELECT | GRANT, REVOKE | COMMIT, ROLLBACK, SAVEPOINT |
| Works Mainly On | Database structure | Table data | Table data | User privileges | Transactions |

---

# 🧠 **10. Easy Way to Remember SQL Commands**

```text
🏗️ DDL
   ↓
Structure banao/change karo
CREATE | ALTER | DROP | TRUNCATE

✏️ DML
   ↓
Data ko manipulate karo
INSERT | UPDATE | DELETE

🔍 DQL
   ↓
Data dekho
SELECT

🔐 DCL
   ↓
Permission control karo
GRANT | REVOKE

🔄 TCL
   ↓
Transaction control karo
COMMIT | ROLLBACK | SAVEPOINT
```

---

# 🧑‍💻 **11. Complete Practical Example**

Sab commands ko ek example se samajhte hain.

### 📌 Step 1 — Database Create

```sql
CREATE DATABASE CollegeDB;
```

### 📌 Step 2 — Database Select

```sql
USE CollegeDB;
```

### 📌 Step 3 — Table Create

```sql
CREATE TABLE Student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Course VARCHAR(30)
);
```

### 📌 Step 4 — Data Insert

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(101, 'Kajal', 18, 'CSE'),
(102, 'Rahul', 19, 'IT'),
(103, 'Priya', 18, 'CSE');
```

### 📌 Step 5 — Data Display

```sql
SELECT * FROM Student;
```

### 📌 Step 6 — Data Update

```sql
UPDATE Student
SET Age = 19
WHERE Roll_No = 101;
```

### 📌 Step 7 — Data Delete

```sql
DELETE FROM Student
WHERE Roll_No = 103;
```

### 📌 Step 8 — New Column Add

```sql
ALTER TABLE Student
ADD Email VARCHAR(100);
```

---

# 📊 **12. Expected Table**

After inserting records:

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | IT |
| 103 | Priya | 18 | CSE |

---

# ⚠️ **13. Important Difference: DELETE vs TRUNCATE vs DROP**

| Feature | DELETE | TRUNCATE | DROP |
|---|---|---|---|
| Removes Rows | Yes | Yes, all rows | Table itself |
| Table Structure | Remains | Remains | Removed |
| `WHERE` | Can be used | Not used | Not used |
| Purpose | Selected/all rows remove | All rows remove | Complete table remove |
| Example | `DELETE FROM Student WHERE...` | `TRUNCATE TABLE Student` | `DROP TABLE Student` |

### 🧠 **Easy Trick**

```text
DELETE
  ↓
Rows Delete

TRUNCATE
  ↓
All Rows Delete
  ↓
Table Remains

DROP
  ↓
Table Delete
```

---

# ⭐ **14. Important Points**

- SQL stands for **Structured Query Language**.
- SQL commands database ke saath communicate karne ke liye use hote hain.
- `CREATE` structure create karta hai.
- `ALTER` structure modify karta hai.
- `DROP` object remove karta hai.
- `TRUNCATE` table ki all rows remove karta hai.
- `INSERT` new data add karta hai.
- `UPDATE` existing data modify karta hai.
- `DELETE` records remove karta hai.
- `SELECT` data retrieve karta hai.
- `GRANT` permissions deta hai.
- `REVOKE` permissions remove karta hai.
- `COMMIT` transaction changes save karta hai.
- `ROLLBACK` uncommitted changes undo karta hai.

---

# ✍️ **15. Exam Point of View**

### ❓ Q1. What is SQL?

**Answer:**

SQL stands for Structured Query Language. It is a standard language used to communicate with and manage data in relational databases.

---

### ❓ Q2. What are SQL Commands?

**Answer:**

SQL Commands are instructions used to perform different operations on a database, such as creating tables, inserting data, retrieving data, updating data and deleting data.

---

### ❓ Q3. What is DDL?

**Answer:**

DDL stands for Data Definition Language. It is used to define and modify the structure of database objects.

**Examples:** `CREATE`, `ALTER`, `DROP`, `TRUNCATE`

---

### ❓ Q4. What is DML?

**Answer:**

DML stands for Data Manipulation Language. It is used to insert, update and delete data in database tables.

**Examples:** `INSERT`, `UPDATE`, `DELETE`

---

### ❓ Q5. What is DQL?

**Answer:**

DQL stands for Data Query Language. It is used to retrieve data from a database.

**Main command:** `SELECT`

---

### ❓ Q6. What is DCL?

**Answer:**

DCL stands for Data Control Language. It is used to control user access and privileges in a database.

**Examples:** `GRANT`, `REVOKE`

---

### ❓ Q7. What is TCL?

**Answer:**

TCL stands for Transaction Control Language. It is used to manage database transactions.

**Examples:** `COMMIT`, `ROLLBACK`, `SAVEPOINT`

---

### ❓ Q8. Difference between DELETE, TRUNCATE and DROP.

**Answer:**

`DELETE` removes rows from a table, `TRUNCATE` removes all rows while keeping the table structure, and `DROP` removes the complete 
---

# 🔄 **17. Quick Revision**

| 🔤 Category | 📝 Commands | 🎯 Purpose |
|---|---|---|
| 🏗️ DDL | `CREATE`, `ALTER`, `DROP`, `TRUNCATE` | Structure |
| ✏️ DML | `INSERT`, `UPDATE`, `DELETE` | Data Manipulation |
| 🔍 DQL | `SELECT` | Data Retrieval |
| 🔐 DCL | `GRANT`, `REVOKE` | Access Control |
| 🔄 TCL | `COMMIT`, `ROLLBACK`, `SAVEPOINT` | Transaction Control |

---

# 🚀 **18. One-Line Revision**

> 💡 **SQL Commands are instructions used to create, manage, retrieve, modify and control data in a database.**

---
