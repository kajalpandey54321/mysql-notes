# 🗄️ CHAPTER 1 — DATABASE BASICS

> 📚 **MySQL Complete Notes**
>
> 💻 **Hinglish Notes | Diploma CSE**
>
> 🎯 Beginner Friendly + Exam Ready

---

## 🌟 Chapter Overview

Is chapter me hum Database aur Database Management System ke basic concepts ko samjhenge.

### 📌 Topics Covered

- 🔹 Data
- 🔹 Information
- 🔹 Database
- 🔹 DBMS
- 🔹 RDBMS
- 🔹 Database Table
- 🔹 Row and Column
- 🔹 DBMS vs RDBMS
- 🔹 Database ke Advantages
- 🔹 Real-Life Examples
- 🔹 Quick Revision
- 🔹 Important Exam Questions

---

# 🔹 1. DATA KYA HOTA HAI?

### 📖 Definition

**Data means raw facts and figures that can be processed to obtain useful information.**

### 🧠 Simple Hinglish

Data ka matlab hota hai **raw facts ya basic information**.

Jab tak data ko process nahi kiya jata, tab tak wo directly useful information nahi bhi ho sakta.

### 📌 Examples

| 🏷️ Information | 📌 Value |
|---|---|
| 👤 Name | Kajal |
| 🎂 Age | 20 |
| 💻 Course | CSE |
| 📝 Marks | 85 |
| 🔢 Roll No. | 101 |
| 📍 City | Jaunpur |

> 💡 **Note:** Ye sab individual facts hain, isliye inhe **Data** kaha ja sakta hai.

---

### 🎯 Real-Life Example

College me student se related information:

- 👤 **Name**
- 🔢 **Roll Number**
- 💻 **Course**
- 📊 **Marks**
- 📍 **Address**

👉 In sabhi information ko collect karke student ka **data** banaya ja sakta hai.

---

### 🧠 Easy Way to Remember

**DATA = Raw Facts & Information**

📌 Example:

**Name + Age + Course + Marks = Student Data**

---

### ✍️ Exam Point of View

**Definition:**  
Data means raw facts and figures that can be processed to obtain meaningful information.

**Hinglish:**  
Data raw facts ya basic information ka collection hota hai, jise process karke useful information obtain ki ja sakti hai.

### 📌 Examples

| 🏷️ Data | 💡 Information |
|---|---|
| 📊 Marks = 85 | 🎓 Student scored 85 marks |
| 🎂 Age = 20 | 👤 Student is 20 years old |
| 💻 Course = CSE | 🎓 Student is studying CSE |
| 🔢 Roll No. = 101 | 🆔 Student's roll number is 101 |
| 📍 City = Jaunpur | 🏠 Student lives in Jaunpur |

> 💡 **Note:** Jab raw data ko process karke uska meaningful result milta hai, to use **Information** kaha jata hai.

---

### 🎯 Real-Life Example

College me students ka raw data collect kiya gaya:

- 👤 **Name:** Kajal
- 🔢 **Roll No.:** 101
- 💻 **Course:** CSE
- 📊 **Marks:** 85

Is data ko process karne ke baad hum keh sakte hain:

👉 **Kajal is a CSE student with Roll No. 101 and scored 85 marks.**




Ye meaningful result **Information** hai.

---

### 🧠 Easy Way to Remember

**DATA → PROCESSING → INFORMATION**

📌 Example:

**Marks = 85** → Raw Data  
⬇️  
**Student scored 85 marks** → Meaningful Information

---

### 🔄 Data vs Information

| 📊 Data | 💡 Information |
|---|---|
| Raw facts hote hain | Processed data hota hai |
| Meaningful hona zaroori nahi | Meaningful hota hai |
| Input ke form me hota hai | Output ke form me milta hai |
| Example: `85` | Example: `Kajal scored 85 marks` |

---

### ✍️ Exam Point of View

**Definition:**  
Information is processed and organized data that provides meaningful and useful knowledge.

**Hinglish:**  
Information wo processed aur organized data hota hai jo hume meaningful aur useful result provide karta hai.

---

### ⭐ Important Point

> 🔥 **Data is the raw material, while Information is the meaningful result obtained after processing the data.**


# 🗄️ DATABASE

### 📖 Definition

A **Database** is an organized collection of related data that can be easily stored, managed, accessed and retrieved.

### 🧠 Simple Hinglish

Database ek **organized collection of data** hota hai.

Simple words me, database ek **digital storage place** ki tarah hota hai jahan hum data ko systematically store karte hain, taaki zarurat padne par data ko easily **search, access, update aur manage** kiya ja sake.

---

### 📌 Examples

| 🏷️ Database | 📂 Stored Data |
|---|---|
| 🏫 College Database | Student records |
| 🏥 Hospital Database | Patient records |
| 🏦 Bank Database | Customer & account details |
| 🛒 Shopping Database | Products & orders |
| 📚 Library Database | Books & members |

> 💡 **Note:** Database me data ko organized form me store kiya jata hai, jisse data ko easily manage kiya ja sake.

---

### 🎯 Real-Life Example

Ek **College Database** me students ki information store ho sakti hai:

- 👤 **Name**
- 🔢 **Roll Number**
- 💻 **Course**
- 📊 **Marks**
- 📍 **Address**
- 📱 **Phone Number**

Example:

| 🆔 ID | 👤 Name | 💻 Course | 📊 Marks |
|---|---|---|---|
| 1 | Kajal | CSE | 85 |
| 2 | Rahul | CSE | 78 |
| 3 | Priya | IT | 90 |

👉 Ye student records ek **Student Database** ka part ho sakte hain.

---

### ⚙️ Database Me Kya-Kya Kar Sakte Hain?

Database ki help se hum:

- ➕ **Add** → New data add kar sakte hain
- 👀 **View** → Data dekh sakte hain
- 🔍 **Search** → Required data find kar sakte hain
- ✏️ **Update** → Existing data change kar sakte hain
- 🗑️ **Delete** → Unwanted data remove kar sakte hain
- 📊 **Organize** → Data ko systematic form me rakh sakte hain

---

### 🌟 Features of Database

- 📦 **Organized Storage**  
  Data ko systematic way me store karta hai.

- 🔍 **Easy Data Access**  
  Required data ko easily find kiya ja sakta hai.

- ✏️ **Easy Updating**  
  Existing data ko easily update kiya ja sakta hai.

- 🔐 **Data Security**  
  Data ko unauthorized access se protect karne me help karta hai.

- ♻️ **Data Management**  
  Large amount of data ko manage karna easy hota hai.

- 📊 **Data Sharing**  
  Authorized users ke beech data share kiya ja sakta hai.

---

### 🧠 Easy Way to Remember

**DATABASE = Organized Collection of Data**

📌 Example:

**Student Data**

⬇️

👤 Name + 🔢 Roll No. + 💻 Course + 📊 Marks

⬇️

🗄️ **Student Database**

---

### 🔄 Data → Database

|# 💻 DBMS — DATABASE MANAGEMENT SYSTEM

### 📖 Full Form

**DBMS = Database Management System**

---

### 📚 Definition

A **DBMS (Database Management System)** is a software system used to create, store, manage, update and retrieve data from a database.

### 🧠 Simple Hinglish

DBMS ek **software/system** hota hai jo database ke data ko manage karta hai.

Iski help se hum database me:

- ➕ Data add kar sakte hain
- 👀 Data dekh sakte hain
- 🔍 Data search kar sakte hain
- ✏️ Data update kar sakte hain
- 🗑️ Data delete kar sakte hain

👉 Simple words me:

**DBMS = Database ko Manage karne wala Software**

---

### 🎯 Real-Life Example

Maan lo ek college me bahut saare students hain.

College ke paas students ka data hai:

| 🆔 Roll No. | 👤 Name | 💻 Course | 📊 Marks |
|---|---|---|---|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | CSE | 78 |
| 103 | Priya | IT | 90 |

Is data ko database me store aur manage karne ke liye **DBMS** ka use kiya ja sakta hai.

👉 Agar college ko Kajal ke marks dekhne hain, to DBMS ki help se data easily retrieve kiya ja sakta hai.

---

### ⚙️ Functions of DBMS

DBMS ke important functions:

#### 1️⃣ Data Storage 📦

DBMS data ko database me store karne me help karta hai.

#### 2️⃣ Data Retrieval 🔍

Required data ko database se retrieve ya access kiya ja sakta hai.

#### 3️⃣ Data Update ✏️

Existing data ko change ya update kiya ja sakta hai.

#### 4️⃣ Data Deletion 🗑️

Unwanted data ko delete kiya ja sakta hai.

#### 5️⃣ Data Security 🔐

DBMS unauthorized users se data ko protect karne me help karta hai.

#### 6️⃣ Data Management ⚙️

Large amount of data ko efficiently manage karne me help karta hai.

#### 7️⃣ Data Sharing 🤝

Authorized users ke beech data share kiya ja sakta hai.

---

### 🌟 Features of DBMS

- 📦 **Data Storage** — Data ko properly store karta hai.
- 🔍 **Easy Access** — Data ko easily access kiya ja sakta hai.
- ✏️ **Easy Update** — Data ko easily modify kiya ja sakta hai.
- 🗑️ **Easy Deletion** — Unwanted data ko remove kiya ja sakta hai.
- 🔐 **Security** — Data security provide karta hai.
- 👥 **Multiple Users** — Multiple authorized users data access kar sakte hain.
- ♻️ **Backup & Recovery** — Data backup aur recovery me help karta hai.
- 📊 **Data Organization** — Data ko organized form me maintain karta hai.

---

### 🧩 Components of DBMS

DBMS environment ke main components:

| 🧩 Component | 📌 Meaning |
|---|---|
| 👨‍💻 User | Jo database ko use karta hai |
| 💻 Software | DBMS software |
| 🗄️ Database | Jahan data store hota hai |
| 🖥️ Hardware | Computer/server etc. |
| 📋 Procedures | Database use karne ke rules |

---

### 📚 Examples of DBMS

Common database management systems:

- 🐬 **MySQL**
- 🏢 **Oracle Database**
- 🪟 **Microsoft SQL Server**
- 🐘 **PostgreSQL**
- 💾 **SQLite**

> 💡 **Note:** MySQL ek popular **Relational Database Management System (RDBMS)** hai.

---

### 🔄 How DBMS Works?

Simple process:

**👤 User**

⬇️

**💻 DBMS**

⬇️

**🗄️ Database**

⬇️

**📊 Required Data**

### 🧠 Easy Explanation

User database se related request karta hai.

👉 DBMS request ko process karta hai.

👉 Database se required data access karta hai.

👉 DBMS user ko result provide karta hai.

---

### ⭐ Advantages of DBMS

#### 🔐 1. Better Security

Database me stored data ko unauthorized access se protect karne me help karta hai.

#### 📊 2. Organized Data

Data ko systematic aur organized way me manage karta hai.

#### 🔍 3. Easy Data Access

Required information ko easily search aur retrieve kiya ja sakta hai.

#### 👥 4. Data Sharing

Multiple authorized users database ko access kar sakte hain.

#### ♻️ 5. Backup and Recovery

Data loss ki situation me backup aur recovery facilities useful hoti hain.

#### ✏️ 6. Easy Data Modification

Data ko easily insert, update aur delete kiya ja sakta hai.

---

### ⚠️ Disadvantages of DBMS

- 💰 DBMS setup aur maintenance ka cost ho sakta hai.
- 🧠 DBMS ko manage karne ke liye trained person ki zarurat ho sakti hai.
- 💾 Large databases ke liye zyada storage required ho sakti hai.
- ⚙️ DBMS system relatively complex ho sakta hai.

---

### 🔄 DBMS vs Traditional File System

| 💻 DBMS | 📁 File System |
|---|---|
| Data organized way me manage hota hai | Files me data store hota hai |
| Data security better ho sakti hai | Security comparatively limited ho sakti hai |
| Data sharing easy hoti hai | Sharing difficult ho sakti hai |
| Data redundancy ko reduce karne me help karta hai | Data duplication ho sakta hai |
| Backup & recovery features available ho sakte hain | Limited facilities ho sakti hain |

---

### 🧠 Easy Way to Remember

**DBMS = CREATE + STORE + MANAGE + UPDATE + RETRIEVE**

📦 Store  
⬇️  
🔍 Retrieve  
⬇️  
✏️ Update  
⬇️  
🗑️ Delete  
⬇️  
🔐 Secure

---

### 🔗 DBMS aur Database ka Relation

**Database** → Jahan data store hota hai. 🗄️

**DBMS** → Jo database ko manage karta hai. 💻

📌 Example:

**Student Database** = Data ka collection

**DBMS** = Student database ko manage karne wala software

---

### ✍️ Exam Point of View

**Definition:**  
A Database Management System (DBMS) is software used to create, store, manage, update and retrieve data from a database.

**Hinglish:**  
DBMS ek software system hai jo database ko create, store, manage, update aur retrieve karne ke liye use hota hai.

---

### 📝 Important Exam Questions

**Q1. What is DBMS?**  
👉 DBMS stands for Database Management System. It is software used to manage data in a database.

**Q2. Write the full form of DBMS.**  
👉 **Database Management System**

**Q3. Write any four functions of DBMS.**  
👉 Data storage, data retrieval, data update and data deletion.

**Q4. Give examples of DBMS.**  
👉 MySQL, Oracle, Microsoft SQL Server and PostgreSQL.

**Q5. What is the difference between Database and DBMS?**  
👉 Database is an organized collection of data, whereas DBMS is software used to manage that database.

---

### 🚀 Quick Revision

> 💻 **DBMS**
>
> **Full Form:** Database Management System  
>
> 📦 Store Data  
> 🔍 Retrieve Data  
> ✏️ Update Data  
> 🗑️ Delete Data  
> 🔐 Provide Security  
> ⚙️ Manage Database

### ⭐ Remember

**DATABASE = Data Store 🗄️**

**DBMS = Database Manage 💻**


# 💻 **RDBMS — RELATIONAL DATABASE MANAGEMENT SYSTEM**

---

## 📖 **Full Form**

**RDBMS = Relational Database Management System**

---

## 📚 **Definition**

An **RDBMS (Relational Database Management System)** is a software system used to store and manage data in the form of related tables.

---

## 🧠 **Simple Hinglish**

RDBMS ek **database management system** hai jo data ko **tables (rows aur columns)** ke form mein store aur manage karta hai.

👉 Simple words mein:

**RDBMS = Tables + Data + Relationships**

---

## 🎯 **Real-Life Example**

| 🆔 Roll No. | 👤 Name | 💻 Course | 📊 Marks |
|---|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | CSE | 78 |
| 103 | Priya | IT | 90 |

> 💡 **Note:** RDBMS mein data tables ke form mein organized hota hai.

---

## ⚙️ **Features of RDBMS**

### 1️⃣ **Table-Based Storage**

Data ko tables ke form mein store kiya jata hai.

### 2️⃣ **Rows and Columns**

Table mein data rows aur columns ke form mein organized hota hai.

### 3️⃣ **Relationships**

Different tables ke beech relationship establish kiya ja sakta hai.

---

## ⭐ **Advantages of RDBMS**

- 📋 Organized Data
- 🔍 Easy Data Access
- 🔗 Relationship Between Tables
- 🔐 Data Security
- 🛡️ Data Integrity

---

## ⚠️ **Disadvantages of RDBMS**

- 🧠 Database design complex ho sakta hai.
- 💾 Large databases ke liye more storage required ho sakti hai.
- ⚙️ Technical knowledge ki zarurat ho sakti hai.

---

## ✍️ **Exam Point of View**

**Definition:**  
An RDBMS is a database management system that stores data in the form of related tables consisting of rows and columns.

**Hinglish:**  
RDBMS ek database management system hai jo data ko related tables mein rows aur columns ke form mein store aur manage karta hai.

---

## 📝 **Important Exam Questions**

**Q1. What is RDBMS?**  
👉 RDBMS is a database management system that stores data in related tables.

**Q2. Write the full form of RDBMS.**  
👉 **Relational Database Management System**

**Q3. Give examples of RDBMS.**  
👉 MySQL, Oracle, PostgreSQL and Microsoft SQL Server.

---

## 🚀 **Quick Revision**

> 🗃️ **RDBMS**
>
> 📋 Table → Data Storage  
> ➡️ Row → Record  
> ⬇️ Column → Field  
> 🔑 Primary Key → Unique Identification  
> 🔗 Foreign Key → Relationship  
> 💻 SQL → Database Management


# 🗃️ **DATABASE TABLE**

---

## 📌 **1. Database Table Kya Hai?**

**Database Table** database ke andar data ko **rows aur columns** ke form mein store karne ka structured way hai.

### 🧠 **Simple Hinglish**

Table ko hum ek **register ya Excel sheet** ki tarah samajh sakte hain.

- **Column** → kis type ki information hai
- **Row** → ek complete record
- **Cell** → ek single value

### 📌 **Example**

Agar hume students ka data store karna hai, to hum `Student` naam ki table bana sakte hain.

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | CSE |
| 103 | Priya | 18 | IT |

Yahan:

- `Roll_No`, `Name`, `Age`, `Course` → **Columns**
- Har student ki complete information → **Row**
- `Kajal`, `18`, `CSE` → **Values**

---

## 🎯 **2. Database Table Ki Need Kyu Hoti Hai?**

Database Table ka use data ko:

1. 📦 **Store** karne ke liye
2. 🗂️ **Organize** karne ke liye
3. 🔍 **Search** karne ke liye
4. ✏️ **Update** karne ke liye
5. ❌ **Delete** karne ke liye
6. 📊 **Manage** karne ke liye

---

# 🧩 **3. Table Ke Main Parts**

Database Table ke important parts:

### 🔹 **1. Row**

Row ko **Record** bhi kaha jata hai.

Ek row mein kisi ek person/object ki complete information hoti hai.

Example:

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |

Ye ek **complete student record** hai.

---

### 🔹 **2. Column**

Column ko **Field** bhi kaha jata hai.

Column kisi particular type ki information ko represent karta hai.

Example:

```text
Roll_No
Name
Age
Course
```

Ye sab **columns** hain.

---

### 🔹 **3. Cell**

Row aur Column ke intersection ko **Cell** kaha jata hai.

Example:

| Roll_No | Name | Age |
|---:|---|---:|
| 101 | Kajal | 18 |

Yahan `Kajal` ek **cell value** hai.

---

# 📊 **4. Table Structure**

```text
                STUDENT TABLE
        ┌─────────┬─────────┬─────┬────────┐
        │ Roll_No │  Name   │ Age │ Course │
        ├─────────┼─────────┼─────┼────────┤
        │   101   │  Kajal  │ 18  │  CSE   │
        │   102   │  Rahul  │ 19  │  CSE   │
        │   103   │  Priya  │ 18  │   IT   │
        └─────────┴─────────┴─────┴────────┘
             ↑         ↑
           Column    Column

        ←──────── Row ────────→
```

> 💡 **Remember:**  
> **Row = Record**  
> **Column = Field**

---

# 🛠️ **5. Database Table Create Karna**

MySQL mein table create karne ke liye **CREATE TABLE** command use hoti hai.

### 📌 **Syntax**

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype
);
```

---

### 📌 **Example**

```sql
CREATE TABLE Student (
    Roll_No INT,
    Name VARCHAR(50),
    Age INT,
    Course VARCHAR(30)
);
```

### 🧠 **Explanation**

| Part | Meaning |
|---|---|
| `CREATE TABLE` | New table create karta hai |
| `Student` | Table ka naam |
| `Roll_No` | Column name |
| `INT` | Data Type |
| `Name` | Column name |
| `VARCHAR(50)` | Text data type |
| `;` | Query ka end |

---

# ➕ **6. Table Mein Data Insert Karna**

Table create hone ke baad usmein data insert karne ke liye **INSERT INTO** command use hoti hai.

### 📌 **Syntax**

```sql
INSERT INTO table_name
(column1, column2, column3)
VALUES
(value1, value2, value3);
```

### 📌 **Example**

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(101, 'Kajal', 18, 'CSE');
```

---

### 📌 **Multiple Records Insert Karna**

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(102, 'Rahul', 19, 'CSE'),
(103, 'Priya', 18, 'IT');
```

---

# 🔍 **7. Table Ka Data Dekhna**

Table ka data dekhne ke liye **SELECT** command use hoti hai.

### 📌 **Query**

```sql
SELECT * FROM Student;
```

### 📊 **Expected Output**

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | CSE |
| 103 | Priya | 18 | IT |

> 💡 `*` ka meaning hai **all columns**.

---

# ✏️ **8. Table Ka Data Update Karna**

Existing record ko change karne ke liye **UPDATE** command use hoti hai.

### 📌 **Example**

Kajal ki age 18 se 19 karni hai:

```sql
UPDATE Student
SET Age = 19
WHERE Roll_No = 101;
```

> ⚠️ **Important:** `WHERE` condition lagana important hai, warna multiple records update ho sakte hain.

---

# ❌ **9. Table Se Data Delete Karna**

Record delete karne ke liye **DELETE** command use hoti hai.

### 📌 **Example**

Roll number 103 ka record delete karna:

```sql
DELETE FROM Student
WHERE Roll_No = 103;
```

---

# 🗑️ **10. Complete Table Delete Karna**

Agar poori table ko delete karna ho to **DROP TABLE** command use hoti hai.

### 📌 **Query**

```sql
DROP TABLE Student;
```

> ⚠️ **Note:** `DROP TABLE` table aur uske andar ka data dono remove kar deta hai.

---

# 🔑 **11. Primary Key**

Table mein kisi record ko **uniquely identify** karne ke liye Primary Key use hoti hai.

Example:

```sql
CREATE TABLE Student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT,
    Course VARCHAR(30)
);
```

Yahan `Roll_No` **Primary Key** hai.

### ⭐ Primary Key Ki Properties

- Unique hoti hai
- Duplicate value nahi honi chahiye
- `NULL` value nahi hoti
- Har record ko uniquely identify karti hai

---

# 🔗 **12. Foreign Key**

Foreign Key ka use **do tables ke beech relationship establish** karne ke liye hota hai.

### 📌 **Example**

```sql
CREATE TABLE Course (
    Course_ID INT PRIMARY KEY,
    Course_Name VARCHAR(50)
);
```

```sql
CREATE TABLE Student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Course_ID INT,
    FOREIGN KEY (Course_ID) REFERENCES Course(Course_ID)
);
```

Yahan `Student` table ka `Course_ID`, `Course` table ke `Course_ID` se connected hai.

---

# ⚙️ **13. Common Operations on Table**

Database Table par mainly ye operations perform kiye ja sakte hain:

| Operation | SQL Command | Purpose |
|---|---|---|
| 🆕 Create | `CREATE TABLE` | Table banana |
| ➕ Insert | `INSERT INTO` | Data add karna |
| 🔍 Read | `SELECT` | Data dekhna |
| ✏️ Update | `UPDATE` | Data change karna |
| ❌ Delete | `DELETE` | Record delete karna |
| 🗑️ Drop | `DROP TABLE` | Complete table delete karna |

### 🧠 **Easy Trick**

```text
CREATE  → Table banao
INSERT  → Data dalo
SELECT  → Data dekho
UPDATE  → Data badlo
DELETE  → Data hatao
DROP    → Table hatao
```

---

# 📋 **14. Table Ki Important Characteristics**

Database Table ki main characteristics:

1. 📌 Table ka ek unique name hota hai.
2. 📌 Table rows aur columns se milkar banti hai.
3. 📌 Har column ka ek name hota hai.
4. 📌 Har column ka ek data type hota hai.
5. 📌 Rows records ko represent karti hain.
6. 📌 Primary Key records ko uniquely identify kar sakti hai.
7. 📌 Tables ke beech relationships create kiye ja sakte hain.

---

# 🆚 **15. Database vs Database Table**

| Feature | Database | Database Table |
|---|---|---|
| Meaning | Data ka organized collection | Database ke andar data store karne ki structure |
| Contains | Tables, views etc. | Rows & Columns |
| Example | `CollegeDB` | `Student` |
| Purpose | Complete data management | Specific data store karna |

### 🧠 **Easy Example**

```text
CollegeDB  ← Database

     ↓

Student    ← Table
Teacher    ← Table
Course     ← Table
```

---

# 🎯 **16. Real-Life Example**

College ke database mein multiple tables ho sakti hain:

```text
                 COLLEGE DATABASE
                        │
        ┌───────────────┼───────────────┐
        ↓               ↓               ↓
     Student          Teacher          Course
      Table             Table           Table
```

### 📌 Student Table

| Roll_No | Name | Course |
|---:|---|---|
| 101 | Kajal | CSE |
| 102 | Rahul | IT |

### 📌 Course Table

| Course_ID | Course_Name |
|---:|---|
| 1 | CSE |
| 2 | IT |

Is tarah database ke andar alag-alag tables mein related information store ki ja sakti hai.

---

# ✍️ **17. Exam Point of View**

### ❓ Q1. What is a Database Table?

**Answer:**

A Database Table is a structured collection of data arranged in the form of rows and columns. It is used to store and organize data in a database.

---

### ❓ Q2. What is a Row?

**Answer:**

A row is a single record in a database table. It contains complete information about one entity or object.

---

### ❓ Q3. What is a Column?

**Answer:**

A column is a field in a database table that represents a particular type of information.

---

### ❓ Q4. How do you create a table in MySQL?

**Answer:**

A table is created in MySQL using the `CREATE TABLE` command.

Example:

```sql
CREATE TABLE Student (
    Roll_No INT,
    Name VARCHAR(50),
    Age INT
);
```

---

### ❓ Q5. What is a Primary Key?

**Answer:**

A Primary Key is a column or set of columns that uniquely identifies each record in a table. It does not allow duplicate or NULL values.

---

### ❓ Q6. What is a Foreign Key?

**Answer:**

A Foreign Key is a column that establishes a relationship between two tables by referring to the Primary Key of another table.

---



# 🧠 **19. Quick Revision**

```text
🗃️ Database Table
        ↓
Rows + Columns
        ↓
Row = Record
Column = Field
Cell = Single Value
        ↓
CREATE TABLE → Table Create
INSERT → Data Add
SELECT → Data Read
UPDATE → Data Change
DELETE → Record Delete
DROP TABLE → Table Delete
        ↓
Primary Key → Unique Identification



# 📊 **ROW AND COLUMN**

---

## 📌 **1. Row and Column Kya Hote Hain?**

Database Table mein data ko properly organize karne ke liye **Rows** aur **Columns** ka use hota hai.

### 🧠 **Simple Hinglish**

- **Row** → Ek complete record/information ko represent karti hai.
- **Column** → Ek particular type ki information ko represent karta hai.

### 📌 **Example**

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | IT |
| 103 | Priya | 18 | CSE |

Is table mein:

- `Roll_No`, `Name`, `Age`, `Course` → **Columns**
- `101, Kajal, 18, CSE` → **First Row**
- `102, Rahul, 19, IT` → **Second Row**
- `103, Priya, 18, CSE` → **Third Row**

---

# 🟦 **2. Row Kya Hai?**

A **Row** database table mein ek **complete record** ko represent karti hai.

Row ko **Record** bhi kaha jata hai.

### 📌 **Example**

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |

Yahan poori line:

```text
101 | Kajal | 18 | CSE
```

ek **Row/Record** hai.

### 🧠 **Easy Way**

> 💡 **Row = Complete Record**

---

# 🔹 **3. Row Ki Characteristics**

Rows ki important characteristics:

1. 📌 Row ek complete record ko represent karti hai.
2. 📌 Ek table mein multiple rows ho sakti hain.
3. 📌 Har row mein columns ke according values hoti hain.
4. 📌 Har row kisi particular entity ki information store kar sakti hai.
5. 📌 Primary Key ki help se rows ko uniquely identify kiya ja sakta hai.

---

# 🟩 **4. Column Kya Hai?**

A **Column** database table mein ek particular type ki information ko represent karta hai.

Column ko **Field** bhi kaha jata hai.

### 📌 **Example**

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | IT |
| 103 | Priya | 18 | CSE |

Yahan:

```text
Roll_No
Name
Age
Course
```

sabhi **Columns** hain.

### 🧠 **Easy Way**

> 💡 **Column = Particular Type of Information**

---

# 🔹 **5. Column Ki Characteristics**

Columns ki important characteristics:

1. 📌 Har column ka ek unique name hona chahiye.
2. 📌 Har column kisi particular type ka data store karta hai.
3. 📌 Har column ka ek data type hota hai.
4. 📌 Column mein multiple rows ki values hoti hain.
5. 📌 Column par constraints apply kiye ja sakte hain.

---

# 📊 **6. Row vs Column**

| Feature | Row | Column |
|---|---|---|
| Meaning | Complete record | Particular field |
| Also called | Record | Field |
| Direction | Horizontal | Vertical |
| Contains | Different columns ki values | Same type ki values |
| Example | `101, Kajal, 18, CSE` | `Name` |
| Purpose | Ek complete entity ka data | Particular information store karna |

---

# ↔️ **7. Horizontal and Vertical**

Row aur Column ko direction se easily identify kar sakte hain.

```text
              COLUMNS
        ↓        ↓       ↓       ↓
     Roll_No    Name     Age    Course
        │         │       │       │
        ├──────────────────────────→ ROW
        │    101   Kajal   18    CSE
        │
        ├──────────────────────────→ ROW
        │    102   Rahul   19    IT
        │
        └──────────────────────────→ ROW
             103   Priya   18    CSE
```

### 🧠 **Remember**

```text
↔️ Horizontal = Row
↕️ Vertical   = Column
```

---

# 🔢 **8. Number of Rows and Columns**

Example:

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |
| 102 | Rahul | 19 | IT |
| 103 | Priya | 18 | CSE |

Is table mein:

- **Rows = 3**
- **Columns = 4**

> 💡 Header ko data row count mein normally include nahi kiya jata.

---

# 🧑‍💻 **9. SQL Mein Row Add Karna**

New row add karne ke liye `INSERT INTO` command use hoti hai.

### 📌 **Query**

```sql
INSERT INTO Student
(Roll_No, Name, Age, Course)
VALUES
(104, 'Aman', 19, 'CSE');
```

### 🧠 **Explanation**

Is query se `Student` table mein ek **new row/record** add hoga.

---

# 🔍 **10. Specific Row Dekhna**

Kisi particular record ko dekhne ke liye `SELECT` ke saath `WHERE` use kar sakte hain.

### 📌 **Query**

```sql
SELECT * FROM Student
WHERE Roll_No = 101;
```

### 📊 **Expected Output**

| Roll_No | Name | Age | Course |
|---:|---|---:|---|
| 101 | Kajal | 18 | CSE |

---

# ✏️ **11. Row Update Karna**

Kisi row ke data ko change karne ke liye `UPDATE` command use hoti hai.

### 📌 **Example**

```sql
UPDATE Student
SET Age = 19
WHERE Roll_No = 101;
```

Isse Roll_No `101` wale student ki age update ho jayegi.

---

# ❌ **12. Row Delete Karna**

Kisi particular row ko delete karne ke liye `DELETE` command use hoti hai.

### 📌 **Query**

```sql
DELETE FROM Student
WHERE Roll_No = 104;
```

Isse Roll_No `104` wali row delete ho jayegi.

> ⚠️ **Important:** `WHERE` condition carefully use karein, warna unwanted rows delete ho sakti hain.

---

# 🧑‍💻 **13. Column Add Karna**

Existing table mein new column add karne ke liye `ALTER TABLE` command use hoti hai.

### 📌 **Example**

Student table mein `Email` column add karna:

```sql
ALTER TABLE Student
ADD Email VARCHAR(100);
```

### 🧠 **Explanation**

- `ALTER TABLE` → Existing table mein change karne ke liye
- `ADD` → New column add karne ke liye
- `Email` → New column ka name
- `VARCHAR(100)` → Column ka data type

---

# ✏️ **14. Column Modify Karna**

Column ka data type ya size change karne ke liye `ALTER TABLE` use kiya ja sakta hai.

### 📌 **Example**

```sql
ALTER TABLE Student
MODIFY Name VARCHAR(100);
```

Isse `Name` column ki maximum length `100` characters kar di jayegi.

---

# ❌ **15. Column Delete Karna**

Table se kisi column ko remove karne ke liye `DROP COLUMN` use hota hai.

### 📌 **Query**

```sql
ALTER TABLE Student
DROP COLUMN Email;
```

Isse `Email` column table se remove ho jayega.

> ⚠️ **Note:** Column drop karne se us column ka stored data bhi remove ho sakta hai.

---

# 📋 **16. Table Ke Columns Dekhna**

MySQL mein table ke columns aur unki details dekhne ke liye:

### 📌 **Query**

```sql
DESCRIBE Student;
```

Ya:

```sql
DESC Student;
```

### 🧠 **Isse kya pata chalega?**

- Column Name
- Data Type
- NULL allowed hai ya nahi
- Key
- Default value
- Extra information

---

# 📊 **17. Rows Ki Count Karna**

Table mein total kitni rows hain, ye check karne ke liye `COUNT()` function use karte hain.

### 📌 **Query**

```sql
SELECT COUNT(*) FROM Student;
```

### 📊 **Example Output**

```text
4
```

Agar table mein 4 student records hain, to result `4` aayega.

---

# 🔢 **18. Columns Ki Count Kaise Samjhein?**

Table ke columns ki information dekhne ke liye:

```sql
DESCRIBE Student;
```

Is command ke output mein table ke saare columns show honge.

---

# 🏫 **19. Real-Life Example**

Student Management System mein ek table ho sakti hai:

| Roll_No | Name | Age | Course | City |
|---:|---|---:|---|---|
| 101 | Kajal | 18 | CSE | Jaunpur |
| 102 | Rahul | 19 | IT | Delhi |
| 103 | Priya | 18 | CSE | Lucknow |

### 📌 Rows

```text
Row 1 → 101 | Kajal | 18 | CSE | Jaunpur
Row 2 → 102 | Rahul | 19 | IT  | Delhi
Row 3 → 103 | Priya | 18 | CSE | Lucknow
```

### 📌 Columns

```text
Roll_No
Name
Age
Course
City
```

---

# ⭐ **20. Row and Column Ka Importance**

### 📌 Rows ka importance

- Complete records store karti hain.
- Individual records ko identify karne mein help karti hain.
- Data ko retrieve, update aur delete karna easy hota hai.

### 📌 Columns ka importance

- Data ko categories mein divide karta hai.
- Data ka type define karta hai.
- Specific information ko search aur manage karna easy banata hai.

---

# 🧠 **21. Easy Way to Remember**

```text
📊 TABLE
   │
   ├── ↔️ ROW
   │      ↓
   │    Record
   │
   └── ↕️ COLUMN
          ↓
        Field
```

### ⭐ **One-Line Trick**

> 💡 **Row = Record**  
> 💡 **Column = Field**

---

# ✍️ **22. Exam Point of View**

### ❓ Q1. What is a Row?

**Answer:**

A row is a complete record in a database table. It contains values for different columns related to one entity.

---

### ❓ Q2. What is a Column?

**Answer:**

A column is a field in a database table that represents a particular type of information.

---

### ❓ Q3. What is another name for Row?

**Answer:**

A Row is also called a **Record**.

---

### ❓ Q4. What is another name for Column?

**Answer:**

A Column is also called a **Field**.

---

### ❓ Q5. What is the difference between Row and Column?

**Answer:**

A row represents a complete record and is arranged horizontally, whereas a column represents a particular field and is arranged vertically.

---

### ❓ Q6. Which command is used to add a new row?

**Answer:**

The `INSERT INTO` command is used to add a new row to a table.

Example:

```sql
INSERT INTO Student
(Roll_No, Name, Age)
VALUES
(101, 'Kajal', 18);
```

---

### ❓ Q7. Which command is used to add a new column?

**Answer:**

The `ALTER TABLE ... ADD` command is used to add a new column.

Example:

```sql
ALTER TABLE Student
ADD Email VARCHAR(100);
```

---

# ⭐ **23. Important Questions**

### 📌 **Short Questions**

1. What is a Row?
2. What is a Column?
3. What is a Record?
4. What is a Field?
5. What is the difference between Row and Column?
6. How can you add a new row in MySQL?
7. How can you add a new column in MySQL?
8. Which command is used to modify a column?
9. Which command is used to delete a column?

### 📌 **Long Questions**

1. Explain Row and Column with a suitable example.
2. Differentiate between Row and Column.
3. Explain different operations performed on Rows and Columns.
4. Explain how to add, modify and delete a column in MySQL.

---

# 🔄 **24. Quick Revision**

| Term | Meaning |
|---|---|
| 📊 Table | Data ka organized structure |
| ↔️ Row | Complete Record |
| ↕️ Column | Particular Field |
| 🔲 Cell | Single Value |
| ➕ Insert | New Row Add |
| ✏️ Update | Existing Data Change |
| ❌ Delete | Row Remove |
| ➕ Add Column | `ALTER TABLE ... ADD` |
| ✏️ Modify Column | `ALTER TABLE ... MODIFY` |
| ❌ Drop Column | `ALTER TABLE ... DROP COLUMN` |
| 🔍 Describe Table | `DESC` / `DESCRIBE` |

---

# 🚀 **25. One-Line Revision**

> 💡 **Row represents a complete record horizontally, while Column represents a particular field vertically in a database table.**

---


