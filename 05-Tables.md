# 🗃️ **05 — TABLES IN MYSQL**

> 💡 **Table** database ke andar data ko **rows aur columns** ke form me store karne ka structure hai.

---

## 📌 1. Table Kya Hoti Hai?

### 🔹 Definition

A **Table** is a collection of related data organized in the form of **rows and columns**.

### 🧠 Easy Hinglish

Database ke andar actual data ko store karne ke liye hum **Table** ka use karte hain.

Example:

Agar `College` naam ka database hai, to uske andar different tables ho sakti hain:

```text
College Database
       │
       ├── Student
       ├── Teacher
       ├── Course
       └── Attendance
```

Yaha `Student`, `Teacher`, `Course` etc. **tables** hain.

---

# 📊 2. Example of a Table

Maan lo `Student` table hai:

| ID | Name | Course | Marks |
|---:|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | CSE | 78 |
| 103 | Priya | IT | 90 |

Is table me:

- `ID` → Column
- `Name` → Column
- `Course` → Column
- `Marks` → Column
- Ek student ki complete information → Row

---

# 🧩 3. Main Parts of a Table

Table ke mainly do important parts hote hain:

### 1️⃣ Row

Row ko **Record** bhi kaha jata hai.

Ye kisi ek complete item/person ki information contain karti hai.

Example:

```text
101 | Kajal | CSE | 85
```

Ye ek complete **row/record** hai.

---

### 2️⃣ Column

Column ko **Field** ya **Attribute** bhi kaha jata hai.

Ye kisi particular type ki information contain karta hai.

Example:

```text
ID
Name
Course
Marks
```

Ye table ke **columns** hain.

---

## 🧠 Easy Trick

> ➡️ **Row = Record**
>
> ⬇️ **Column = Field**

---

# 🏗️ 4. CREATE TABLE

## 📖 Definition

`CREATE TABLE` command ka use database ke andar **new table create** karne ke liye kiya jata hai.

### 📝 Syntax

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype
);
```

---

## 💻 Example

```sql
CREATE TABLE Student (
    id INT,
    name VARCHAR(50),
    course VARCHAR(50),
    marks INT
);
```

Isse `Student` naam ki table create hogi.

---

# 🔍 5. SHOW TABLES

## 📖 Definition

`SHOW TABLES` command selected database ke andar available **tables ki list** show karta hai.

### 💻 Example

```sql
SHOW TABLES;
```

### 📌 Example Output

```text
Student
Teacher
Course
Attendance
```

> 💡 Pehle database select karna useful hota hai:
>
> ```sql
> USE College;
> ```

---

# 🔎 6. DESCRIBE TABLE

Table ki structure dekhne ke liye `DESCRIBE` ya `DESC` command use kar sakte hain.

### 📝 Syntax

```sql
DESCRIBE table_name;
```

Ya:

```sql
DESC table_name;
```

### 💻 Example

```sql
DESC Student;
```

### 📌 Isse kya pata chalega?

- Column name
- Data type
- NULL allowed hai ya nahi
- Key information
- Default value
- Other column properties

---

# ➕ 7. INSERT DATA INTO TABLE

Table create karne ke baad usme data insert karna hota hai.

Iske liye `INSERT INTO` command use hoti hai.

### 📝 Syntax

```sql
INSERT INTO table_name
VALUES (value1, value2, value3);
```

---

## 💻 Example

```sql
INSERT INTO Student
VALUES (101, 'Kajal', 'CSE', 85);
```

Multiple records bhi insert kar sakte hain:

```sql
INSERT INTO Student
VALUES
(101, 'Kajal', 'CSE', 85),
(102, 'Rahul', 'CSE', 78),
(103, 'Priya', 'IT', 90);
```

---

# 👀 8. SELECT DATA FROM TABLE

Table ka data dekhne ke liye `SELECT` command use hoti hai.

### 📝 Syntax

```sql
SELECT * FROM table_name;
```

### 💻 Example

```sql
SELECT * FROM Student;
```

### 📌 Output

| ID | Name | Course | Marks |
|---:|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | CSE | 78 |
| 103 | Priya | IT | 90 |

> 💡 `*` ka meaning hai **all columns**.

---

# 🎯 9. Specific Columns Display Karna

Agar hume sirf kuch columns chahiye, to unke names likh sakte hain.

### 💻 Example

```sql
SELECT name, course
FROM Student;
```

### 📌 Output

| Name | Course |
|---|---|
| Kajal | CSE |
| Rahul | CSE |
| Priya | IT |

---

# ✏️ 10. UPDATE TABLE DATA

Existing data ko change/update karne ke liye `UPDATE` command use hoti hai.

### 📝 Syntax

```sql
UPDATE table_name
SET column_name = new_value
WHERE condition;
```

### 💻 Example

Rahul ke marks ko 82 karna:

```sql
UPDATE Student
SET marks = 82
WHERE id = 102;
```

> ⚠️ **Important:** `UPDATE` ke saath `WHERE` condition carefully use karein. `WHERE` na hone par multiple/all rows update ho sakti hain.

---

# 🗑️ 11. DELETE DATA FROM TABLE

Table se records delete karne ke liye `DELETE` command use hoti hai.

### 📝 Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### 💻 Example

Student ID 103 ko delete karna:

```sql
DELETE FROM Student
WHERE id = 103;
```

---

# ➕ 12. ALTER TABLE

`ALTER TABLE` ka use existing table ki **structure modify** karne ke liye kiya jata hai.

Isse hum:

- New column add kar sakte hain
- Column remove kar sakte hain
- Column modify kar sakte hain
- Column rename kar sakte hain

---

## 12.1 Add New Column

### 📝 Syntax

```sql
ALTER TABLE table_name
ADD column_name datatype;
```

### 💻 Example

Student table me `city` column add karna:

```sql
ALTER TABLE Student
ADD city VARCHAR(50);
```

---

## 12.2 Add Multiple Columns

```sql
ALTER TABLE Student
ADD email VARCHAR(100),
ADD phone VARCHAR(15);
```

---

# ✏️ 13. MODIFY COLUMN

Existing column ka data type ya definition modify karne ke liye `MODIFY` use kar sakte hain.

### 💻 Example

```sql
ALTER TABLE Student
MODIFY name VARCHAR(100);
```

Yaha `name` column ka size change kiya gaya hai.

> 💡 Exact `ALTER TABLE` syntax MySQL version aur change ki requirement par depend kar sakta hai.

---

# 🔄 14. RENAME COLUMN

Column ka naam change karne ke liye MySQL me `RENAME COLUMN` use kiya ja sakta hai.

### 📝 Syntax

```sql
ALTER TABLE table_name
RENAME COLUMN old_name TO new_name;
```

### 💻 Example

```sql
ALTER TABLE Student
RENAME COLUMN name TO student_name;
```

Ab `name` ki jagah `student_name` column ho jayega.

---

# 🗑️ 15. DROP COLUMN

Table se kisi column ko permanently remove karne ke liye `DROP COLUMN` use hota hai.

### 📝 Syntax

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

### 💻 Example

```sql
ALTER TABLE Student
DROP COLUMN city;
```

Isse `city` column table se remove ho jayega.

> ⚠️ **Important:** Column drop karne se us column ka stored data bhi remove ho sakta hai.

---

# 🔄 16. RENAME TABLE

Existing table ka naam change karne ke liye `RENAME TABLE` use kar sakte hain.

### 📝 Syntax

```sql
RENAME TABLE old_table_name
TO new_table_name;
```

### 💻 Example

```sql
RENAME TABLE Student
TO Students;
```

Ab table ka naam `Students` ho jayega.

---

# 🧹 17. TRUNCATE TABLE

`TRUNCATE TABLE` ka use table ke **all rows remove** karne ke liye kiya jata hai, while table structure remains available.

### 📝 Syntax

```sql
TRUNCATE TABLE table_name;
```

### 💻 Example

```sql
TRUNCATE TABLE Student;
```

Iske baad table empty ho jayegi, lekin table structure rahega.

---

# 🗑️ 18. DROP TABLE

`DROP TABLE` ka use complete table ko delete karne ke liye hota hai.

### 📝 Syntax

```sql
DROP TABLE table_name;
```

### 💻 Example

```sql
DROP TABLE Student;
```

Isse `Student` table aur uski structure/data remove ho sakti hai.

---

# ⚖️ 19. DELETE vs TRUNCATE vs DROP TABLE

| Feature | DELETE | TRUNCATE | DROP TABLE |
|---|---|---|---|
| Purpose | Rows delete | All rows remove | Complete table remove |
| Table Structure | Remains | Remains | Removed |
| WHERE | Yes | No | No |
| Example | `DELETE FROM Student WHERE id=101;` | `TRUNCATE TABLE Student;` | `DROP TABLE Student;` |

### 🧠 Easy Way

> 🧹 **DELETE → Rows hatao**
>
> 🧹 **TRUNCATE → Saari rows hatao**
>
> 🗑️ **DROP → Puri table hatao**

---

# 🔐 20. PRIMARY KEY IN TABLE

Table me ek column ko **Primary Key** banaya ja sakta hai.

Primary Key ka use each record ko **uniquely identify** karne ke liye hota hai.

### 💻 Example

```sql
CREATE TABLE Student (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    course VARCHAR(50),
    marks INT
);
```

Yaha `id` Primary Key hai.

### 📌 Example

| ID | Name | Course |
|---:|---|---|
| 101 | Kajal | CSE |
| 102 | Rahul | CSE |
| 103 | Priya | IT |

Har student ka `id` unique hona chahiye.

---

# 🔗 21. FOREIGN KEY IN TABLE

Foreign Key ka use tables ke beech **relationship establish** karne ke liye kiya jata hai.

### 💻 Example

```sql
CREATE TABLE Course (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(50)
);
```

Ab Student table:

```sql
CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    name VARCHAR(50),
    course_id INT,
    FOREIGN KEY (course_id)
    REFERENCES Course(course_id)
);
```

Yaha:

```text
Course
  │
  │ course_id
  ↓
Student
```

`course_id` Student table me **Foreign Key** hai.

---

# 🧱 22. Table with Constraints

Table create karte time constraints bhi use kiye ja sakte hain.

### 💻 Example

```sql
CREATE TABLE Student (
    id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    marks INT CHECK (marks >= 0)
);
```

### 📌 Yaha:

| Constraint | Purpose |
|---|---|
| `PRIMARY KEY` | Unique identification |
| `NOT NULL` | Value required |
| `UNIQUE` | Duplicate values prevent karne me help |
| `CHECK` | Condition enforce karta hai |

---

# 🎯 23. Complete Table Example

Ab ek complete practical example dekhte hain.

### Step 1 — Database Create

```sql
CREATE DATABASE College;
```

### Step 2 — Database Select

```sql
USE College;
```

### Step 3 — Table Create

```sql
CREATE TABLE Student (
    id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    course VARCHAR(50),
    marks INT
);
```

### Step 4 — Data Insert

```sql
INSERT INTO Student
VALUES
(101, 'Kajal', 'CSE', 85),
(102, 'Rahul', 'CSE', 78),
(103, 'Priya', 'IT', 90);
```

### Step 5 — Data Display

```sql
SELECT * FROM Student;
```

### Step 6 — Data Update

```sql
UPDATE Student
SET marks = 88
WHERE id = 101;
```

### Step 7 — Data Delete

```sql
DELETE FROM Student
WHERE id = 103;
```

### Step 8 — Structure Check

```sql
DESC Student;
```

---

# 🧠 24. Table ka Basic Structure

```text
                 STUDENT TABLE
┌────────┬────────┬────────┬────────┐
│   ID   │  NAME  │ COURSE │ MARKS  │
├────────┼────────┼────────┼────────┤
│  101   │ Kajal  │  CSE   │   85   │
│  102   │ Rahul  │  CSE   │   78   │
│  103   │ Priya  │  IT    │   90   │
└────────┴────────┴────────┴────────┘
      ↑
    Columns

Each horizontal line = Row / Record
```

---

# 🌍 25. Real-Life Examples of Tables

Real-world applications me different types ki tables ho sakti hain.

### 🏫 College Database

```text
Student
Teacher
Course
Attendance
Result
```

### 🛒 Shopping Website

```text
Customers
Products
Orders
Payments
```

### 🏥 Hospital

```text
Patients
Doctors
Appointments
Medicines
```

### 🏦 Bank

```text
Customers
Accounts
Transactions
Loans
```

---

# ⭐ 26. Advantages of Using Tables

### 1️⃣ Organized Data

Data rows aur columns me properly organized hota hai.

### 2️⃣ Easy Searching

SQL queries ki help se required data easily search kar sakte hain.

### 3️⃣ Easy Updating

Existing data ko update kar sakte hain.

### 4️⃣ Easy Deletion

Unwanted records ko delete kar sakte hain.

### 5️⃣ Data Relationships

Different tables ke beech relationships create ki ja sakti hain.

### 6️⃣ Data Integrity

Constraints ki help se data ko valid aur consistent rakhne me help milti hai.

---

# 📌 27. Important Points

- Table database ke andar data store karti hai.
- Table me **rows aur columns** hote hain.
- Row ko **Record** bhi kaha jata hai.
- Column ko **Field/Attribute** bhi kaha jata hai.
- `CREATE TABLE` → New table create karta hai.
- `SHOW TABLES` → Tables ki list show karta hai.
- `DESC` → Table structure show karta hai.
- `INSERT` → Data add karta hai.
- `SELECT` → Data display karta hai.
- `UPDATE` → Existing data modify karta hai.
- `DELETE` → Rows delete karta hai.
- `ALTER TABLE` → Table structure modify karta hai.
- `TRUNCATE` → All rows remove karta hai, structure remains.
- `DROP TABLE` → Complete table remove karta hai.
- Primary Key record ko uniquely identify karti hai.
- Foreign Key tables ke beech relationship establish karne me help karti hai.

---

# 📝 28. Exam Point of View

## ⭐ 2 Marks Questions

### Q1. What is a table?

**Answer:**  
A table is a database object used to store related data in the form of rows and columns.

---

### Q2. What is a row?

**Answer:**  
A row is a horizontal collection of related values in a table. It is also called a record.

---

### Q3. What is a column?

**Answer:**  
A column is a vertical collection of values representing a particular field or attribute.

---

### Q4. What is the use of CREATE TABLE?

**Answer:**  
`CREATE TABLE` command is used to create a new table in a database.

---

### Q5. What is the use of ALTER TABLE?

**Answer:**  
`ALTER TABLE` is used to modify the structure of an existing table.

---

## ⭐ 5 Marks Question

### Q. Explain table and its important commands in MySQL.

### Answer:

A **table** is a database object used to store related data in the form of rows and columns.

Important table commands are:

1. **CREATE TABLE** – Creates a new table.
2. **SHOW TABLES** – Displays available tables.
3. **DESC** – Displays table structure.
4. **INSERT** – Adds data to a table.
5. **SELECT** – Displays data from a table.
6. **UPDATE** – Modifies existing data.
7. **DELETE** – Deletes records.
8. **ALTER TABLE** – Modifies table structure.
9. **TRUNCATE** – Removes all rows.
10. **DROP TABLE** – Deletes the complete table.

---

# ❓ 29. Important Exam Questions

### 🔹 Short Questions

1. What is a table?
2. What is a row?
3. What is a column?
4. What is a record?
5. What is a field?
6. What is `CREATE TABLE`?
7. What is `SHOW TABLES`?
8. What is `DESC`?
9. What is `ALTER TABLE`?
10. What is `TRUNCATE TABLE`?
11. What is `DROP TABLE`?
12. What is the use of Primary Key?

### 🔹 Long Questions

1. Explain table in MySQL with example.
2. Explain different table-related commands with syntax and examples.
3. Explain `CREATE TABLE`, `INSERT`, `SELECT`, `UPDATE` and `DELETE`.
4. Explain `ALTER TABLE` with its important operations.
5. Differentiate between DELETE, TRUNCATE and DROP.
6. Explain Primary Key and Foreign Key with example.

---

# ⚡ 30. Quick Revision

| 🧩 Command | 🎯 Use |
|---|---|
| `CREATE TABLE` | 🆕 Table create |
| `SHOW TABLES` | 👀 Tables show |
| `DESC` | 🔍 Structure show |
| `INSERT` | ➕ Data add |
| `SELECT` | 👀 Data display |
| `UPDATE` | ✏️ Data change |
| `DELETE` | 🗑️ Rows delete |
| `ALTER TABLE` | 🔧 Structure modify |
| `TRUNCATE` | 🧹 All rows remove |
| `DROP TABLE` | 🗑️ Complete table remove |
| `RENAME TABLE` | 🔄 Table name change |

---

# 🧠 Easy Trick to Remember

> 🆕 **CREATE** → Table banao  
> 👀 **SELECT** → Data dekho  
> ➕ **INSERT** → Data add karo  
> ✏️ **UPDATE** → Data change karo  
> 🗑️ **DELETE** → Row hatao  
> 🔧 **ALTER** → Structure change karo  
> 🧹 **TRUNCATE** → Saari rows hatao  
> ❌ **DROP** → Puri table hatao

---

# 🎯 One-Line Summary

> **A Table is a structured collection of data arranged in rows and columns inside a database.**

---

# 🐬 **END OF 05 — TABLES**
