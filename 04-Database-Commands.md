# 🗄️ **04 — DATABASE COMMANDS**

> 💡 **Database Commands** ka use database ko **create, select, view, modify aur delete** karne ke liye kiya jata hai.

---

## 📌 1. Database Commands Kya Hote Hain?

Database Commands wo **SQL commands** hote hain jinki help se hum database ko manage karte hain.

In commands ka use karke hum:

- 🆕 Database create kar sakte hain
- 🔍 Database dekh sakte hain
- 📂 Database select/use kar sakte hain
- 🔄 Database ko modify kar sakte hain
- 🗑️ Database delete kar sakte hain

### 🧠 Simple Example

Maan lo hume ek college ke students ka data store karna hai.

Sabse pehle hum ek database banayenge:

```sql
CREATE DATABASE College;
```

Phir us database ko use karenge:

```sql
USE College;
```

Ab `College` database ke andar tables bana sakte hain.

---

# 🧩 2. Important Database Commands

MySQL me commonly used database commands hain:

| 🔢 Command | 📌 Use |
|---|---|
| `CREATE DATABASE` | New database create karne ke liye |
| `SHOW DATABASES` | Available databases dekhne ke liye |
| `USE` | Kisi database ko select karne ke liye |
| `DROP DATABASE` | Database delete karne ke liye |
| `ALTER DATABASE` | Database ki properties modify karne ke liye |
| `SHOW TABLES` | Selected database ki tables dekhne ke liye |

---

# 🆕 3. CREATE DATABASE

## 📖 Definition

`CREATE DATABASE` command ka use **new database create** karne ke liye kiya jata hai.

### 📝 Syntax

```sql
CREATE DATABASE database_name;
```

### 💻 Example

```sql
CREATE DATABASE College;
```

Isse `College` naam ka new database create ho jayega.

### 📌 Another Example

```sql
CREATE DATABASE StudentDB;
```

---

## ⚠️ IF NOT EXISTS

Agar hume sure nahi hai ki database pehle se exist karta hai ya nahi, to `IF NOT EXISTS` use kar sakte hain.

```sql
CREATE DATABASE IF NOT EXISTS College;
```

### 💡 Meaning

Agar `College` database already exist karta hai, to MySQL unnecessary error se bachne me help karta hai.

---

# 👀 4. SHOW DATABASES

## 📖 Definition

`SHOW DATABASES` command ka use MySQL server me available **sabhi databases ki list dekhne** ke liye kiya jata hai.

### 📝 Syntax

```sql
SHOW DATABASES;
```

### 💻 Example

```sql
SHOW DATABASES;
```

### 📌 Example Output

```text
information_schema
mysql
performance_schema
sys
College
StudentDB
```

> 💡 **Note:** Output me databases ki list system aur user-created databases ke according different ho sakti hai.

---

# 📂 5. USE DATABASE

## 📖 Definition

`USE` command ka use kisi particular database ko **select/activate** karne ke liye kiya jata hai.

### 📝 Syntax

```sql
USE database_name;
```

### 💻 Example

```sql
USE College;
```

Ab jo bhi table-related commands run karenge, wo normally `College` database ke context me execute hongi.

---

## 🎯 Example

```sql
CREATE DATABASE College;

USE College;
```

Ab hum `College` ke andar table create kar sakte hain:

```sql
CREATE TABLE Student (
    id INT,
    name VARCHAR(50),
    course VARCHAR(50)
);
```

---

# 🗑️ 6. DROP DATABASE

## 📖 Definition

`DROP DATABASE` command ka use **complete database ko delete** karne ke liye kiya jata hai.

### 📝 Syntax

```sql
DROP DATABASE database_name;
```

### 💻 Example

```sql
DROP DATABASE College;
```

Isse `College` database aur uske andar stored tables/data delete ho jayenge.

> ⚠️ **Important:** `DROP DATABASE` ek destructive command hai. Isko use karne se database ka data permanently remove ho sakta hai.

---

## 🛡️ IF EXISTS

Database exist karta hai ya nahi, check karne ke liye:

```sql
DROP DATABASE IF EXISTS College;
```

Isse database exist na hone par unnecessary error ko avoid karne me help milti hai.

---

# ⚙️ 7. ALTER DATABASE

## 📖 Definition

`ALTER DATABASE` command ka use database ki kuch **properties/characteristics modify** karne ke liye kiya ja sakta hai.

### 📝 General Syntax

```sql
ALTER DATABASE database_name
characteristics;
```

MySQL me database-level options version/configuration ke according limited ho sakte hain.

### 💡 Important

Beginner level par `CREATE DATABASE`, `SHOW DATABASES`, `USE` aur `DROP DATABASE` commands sabse important hain.

---

# 📋 8. SHOW TABLES

## 📖 Definition

`SHOW TABLES` command ka use selected database ke andar available **tables ki list dekhne** ke liye kiya jata hai.

### 📝 Syntax

```sql
SHOW TABLES;
```

### 💻 Example

```sql
USE College;

SHOW TABLES;
```

### 📌 Example Output

```text
Student
Teacher
Course
```

> 💡 `SHOW TABLES` tab useful hai jab aap check karna chahte ho ki database ke andar kaun-kaun si tables available hain.

---

# 🔎 9. DESCRIBE TABLE

Database command nahi, lekin database ke andar table ki **structure dekhne ke liye bahut important** command hai.

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

### 📌 Example Output

```text
Field       Type          Null    Key
id          int           YES
name        varchar(50)   YES
course      varchar(50)   YES
```

---

# 🧪 10. Complete Practical Example

Ab ek complete example dekhte hain.

### Step 1 — Database Create

```sql
CREATE DATABASE College;
```

---

### Step 2 — Databases Check

```sql
SHOW DATABASES;
```

---

### Step 3 — Database Select

```sql
USE College;
```

---

### Step 4 — Table Create

```sql
CREATE TABLE Student (
    id INT,
    name VARCHAR(50),
    course VARCHAR(50),
    marks INT
);
```

---

### Step 5 — Tables Check

```sql
SHOW TABLES;
```

---

### Step 6 — Table Structure Check

```sql
DESC Student;
```

---

### Step 7 — Data Insert

```sql
INSERT INTO Student
VALUES
(101, 'Kajal', 'CSE', 85),
(102, 'Rahul', 'CSE', 78),
(103, 'Priya', 'IT', 90);
```

---

### Step 8 — Data Display

```sql
SELECT * FROM Student;
```

### 📌 Output

| ID | Name | Course | Marks |
|---:|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | CSE | 78 |
| 103 | Priya | IT | 90 |

---

# 🔄 11. Database Commands ka Flow

Database ke saath kaam karne ka basic flow:

```text
CREATE DATABASE
       ↓
SHOW DATABASES
       ↓
USE DATABASE
       ↓
CREATE TABLE
       ↓
INSERT DATA
       ↓
SELECT DATA
       ↓
UPDATE / DELETE DATA
```

### 🧠 Easy Way

**Create → Show → Use → Table → Data**

---

# ⚖️ 12. DROP DATABASE vs DROP TABLE

Dono commands delete karne ke liye use hoti hain, lekin difference important hai.

| Feature | `DROP DATABASE` | `DROP TABLE` |
|---|---|---|
| Deletes | Complete database | Only one table |
| Tables | Database ki all tables remove ho sakti hain | Sirf selected table |
| Data | Database ka data remove ho sakta hai | Table ka data remove hota hai |
| Example | `DROP DATABASE College;` | `DROP TABLE Student;` |

### 🧠 Remember

> 🗄️ **DROP DATABASE → Pura Database**
>
> 📋 **DROP TABLE → Sirf Table**

---

# ⚠️ 13. DELETE vs TRUNCATE vs DROP

Ye exam me bahut important comparison hai.

| Command | Kya remove karta hai? | Structure |
|---|---|---|
| `DELETE` | Selected/all rows | Table structure remains |
| `TRUNCATE` | Table ke all rows | Table structure remains |
| `DROP` | Table/database itself | Structure also removed |

### Example

```sql
DELETE FROM Student;
```

```sql
TRUNCATE TABLE Student;
```

```sql
DROP TABLE Student;
```

> 💡 **Important:** `DROP` sabse major removal operation hai because object itself remove ho jata hai.

---

# 🧠 14. Real-Life Example

Maan lo ek college ke paas database hai:

```text
College Database
       │
       ├── Student
       ├── Teacher
       ├── Course
       └── Attendance
```

Database create karne ke liye:

```sql
CREATE DATABASE College;
```

Database select karne ke liye:

```sql
USE College;
```

Tables dekhne ke liye:

```sql
SHOW TABLES;
```

Agar database ki zarurat nahi hai:

```sql
DROP DATABASE College;
```

---

# 📌 15. Important Points

- `CREATE DATABASE` → New database create karta hai.
- `SHOW DATABASES` → Available databases show karta hai.
- `USE` → Database ko select karta hai.
- `DROP DATABASE` → Complete database delete karta hai.
- `SHOW TABLES` → Selected database ki tables show karta hai.
- `DESC` / `DESCRIBE` → Table ki structure show karta hai.
- SQL commands generally `;` se end ki jati hain.
- `DROP DATABASE` use karte time carefully check karna chahiye.
- `USE database_name;` ke baad database current working database ban jata hai.

---

# 📝 16. Exam Point of View

### ⭐ 2 Marks Questions

**Q1. What is CREATE DATABASE command?**

**Answer:**  
`CREATE DATABASE` is used to create a new database in a database management system.

---

**Q2. What is the use of SHOW DATABASES?**

**Answer:**  
`SHOW DATABASES` command is used to display the list of available databases.

---

**Q3. What is the use of USE command?**

**Answer:**  
`USE` command is used to select a particular database for performing operations on it.

---

**Q4. What is DROP DATABASE?**

**Answer:**  
`DROP DATABASE` is used to delete a complete database along with its database objects.

---

### ⭐ 5 Marks Question

**Q. Explain important database commands in MySQL.**

### Answer:

MySQL provides several commands for managing databases. Important database commands are:

1. **CREATE DATABASE** – Used to create a new database.
   ```sql
   CREATE DATABASE College;
   ```

2. **SHOW DATABASES** – Used to display available databases.
   ```sql
   SHOW DATABASES;
   ```

3. **USE** – Used to select a database.
   ```sql
   USE College;
   ```

4. **DROP DATABASE** – Used to delete a complete database.
   ```sql
   DROP DATABASE College;
   ```

5. **SHOW TABLES** – Used to display tables of the selected database.
   ```sql
   SHOW TABLES;
   ```

These commands help in creating and managing databases in MySQL.

---

# ❓ 17. Important Exam Questions

### 🔹 Short Questions

1. What is a database command?
2. What is the use of `CREATE DATABASE`?
3. What is the use of `SHOW DATABASES`?
4. What is the purpose of `USE` command?
5. What is `DROP DATABASE`?
6. What is the use of `SHOW TABLES`?
7. What is the difference between `DROP DATABASE` and `DROP TABLE`?
8. What is the use of `DESC` command?

### 🔹 Long Questions

1. Explain different database commands in MySQL with examples.
2. Explain `CREATE DATABASE`, `SHOW DATABASES`, `USE` and `DROP DATABASE`.
3. Differentiate between `DELETE`, `TRUNCATE` and `DROP`.
4. Explain the steps for creating and using a database in MySQL.

---

# ⚡ 18. Quick Revision

| 🧩 Command | 🎯 Purpose |
|---|---|
| `CREATE DATABASE` | 🆕 Database create |
| `SHOW DATABASES` | 👀 Databases show |
| `USE` | 📂 Database select |
| `DROP DATABASE` | 🗑️ Database delete |
| `SHOW TABLES` | 📋 Tables show |
| `DESC` | 🔍 Table structure show |

---

# 🧠 Easy Trick to Remember

> 🆕 **CREATE** → Database banao  
> 👀 **SHOW** → Database dekho  
> 📂 **USE** → Database select karo  
> 🗑️ **DROP** → Database hatao  
> 📋 **SHOW TABLES** → Tables dekho  
> 🔍 **DESC** → Table structure dekho

---

# 🎯 One-Line Summary

> **Database Commands are SQL commands used to create, select, view and manage databases in MySQL.**

---
# 🐬 **END OF 04 — DATABASE COMMANDS**
