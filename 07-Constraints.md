# 🔒 **07 — CONSTRAINTS IN MYSQL**

> 💡 **Constraint** ka use table ke data par **rules/restrictions** lagane ke liye hota hai, taaki database mein **correct aur valid data** store ho.

---

## 📌 What is Constraint?

### 📝 Definition

A **Constraint** is a rule applied to a column or table to control the type of data that can be stored in a database.

### 💡 Hinglish Explanation

Constraint ko simple language mein **database ka rule** samajh sakte hain.

Jaise college mein rules hote hain:
- Roll number unique hona chahiye.
- Student ka name empty nahi hona chahiye.
- Age valid honi chahiye.

Waise hi database mein constraints data ko valid aur organized rakhte hain.

---

# 🎯 Why Do We Use Constraints?

Constraints ka main purpose hai:

- ✅ **Invalid data ko prevent karna**
- ✅ **Duplicate data ko control karna**
- ✅ **Required field ko compulsory banana**
- ✅ **Tables ke beech relationship maintain karna**
- ✅ **Data accuracy maintain karna**
- ✅ **Data integrity maintain karna**

---

# 📚 Types of Constraints

MySQL mein commonly used constraints:

| 🔢 No. | 🔒 Constraint | 📝 Purpose |
|---|---|---|
| 1️⃣ | **PRIMARY KEY** | Har record ko uniquely identify karta hai |
| 2️⃣ | **FOREIGN KEY** | Tables ke beech relationship banata hai |
| 3️⃣ | **NOT NULL** | Column ko empty/NULL hone se rokta hai |
| 4️⃣ | **UNIQUE** | Duplicate values ko rokta hai |
| 5️⃣ | **CHECK** | Condition ke according data allow karta hai |
| 6️⃣ | **DEFAULT** | Value na dene par default value set karta hai |

---

# 1️⃣ 🔑 PRIMARY KEY

## 📌 Meaning

**Primary Key** ek column ya columns ka combination hota hai jo table ke **har record ko uniquely identify** karta hai.

### 💡 Example

Student table:

| Roll_No | Name | Course |
|---:|---|---|
| 101 | Kajal | CSE |
| 102 | Rahul | IT |
| 103 | Aman | CSE |

Yahaan `Roll_No` har student ke liye different hai, isliye ise **Primary Key** banaya ja sakta hai.

### 🔹 SQL Example

```sql
CREATE TABLE Student (
    Roll_No INT PRIMARY KEY,
    Name VARCHAR(50),
    Course VARCHAR(30)
);
```

### ⭐ Important Points

- Primary Key ki value **unique** hoti hai.
- Primary Key **NULL** nahi ho sakti.
- Ek table mein generally **one PRIMARY KEY constraint** hota hai.
- Ye records ko uniquely identify karta hai.

---

# 2️⃣ 🔗 FOREIGN KEY

## 📌 Meaning

**Foreign Key** ek table ka column hota hai jo kisi doosre table ki **Primary Key ko reference** karta hai.

Iska main purpose tables ke beech **relationship establish** karna hai.

### 💡 Example

### Student Table

| Student_ID | Name |
|---:|---|
| 101 | Kajal |
| 102 | Rahul |

### Marks Table

| Mark_ID | Student_ID | Marks |
|---:|---:|---:|
| 1 | 101 | 85 |
| 2 | 102 | 78 |

Yahaan `Marks.Student_ID`, `Student.Student_ID` ko reference kar raha hai.

### 🔹 SQL Example

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```

```sql
CREATE TABLE Marks (
    Mark_ID INT PRIMARY KEY,
    Student_ID INT,
    Marks INT,
    FOREIGN KEY (Student_ID)
        REFERENCES Student(Student_ID)
);
```

### ⭐ Important Points

- Foreign Key tables ke beech relationship banati hai.
- Ye generally doosri table ki Primary Key ko reference karti hai.
- Related data ki **referential integrity** maintain karne mein help karti hai.

---

# 3️⃣ 🚫 NOT NULL

## 📌 Meaning

**NOT NULL** constraint kisi column ko `NULL` value accept karne se rokta hai.

### 💡 Example

Student ka name compulsory hai.

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL
);
```

Agar `Name` provide nahi kiya gaya, to record insert karte waqt error aa sakta hai.

### ⭐ Real-Life Example

College admission form mein:

```text
Name → Required
Email → Required
Phone → Required
```

Required field ko database mein `NOT NULL` se enforce kiya ja sakta hai.

---

# 4️⃣ 🆔 UNIQUE

## 📌 Meaning

**UNIQUE** constraint kisi column mein **duplicate values** ko prevent karta hai.

### 💡 Example

Email har student ka different hona chahiye.

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Email VARCHAR(100) UNIQUE
);
```

Agar same email dobara insert karne ki koshish ki jaaye, to MySQL duplicate value ko reject kar sakta hai.

### ⭐ Primary Key vs UNIQUE

| PRIMARY KEY | UNIQUE |
|---|---|
| Record ko uniquely identify karta hai | Duplicate values ko prevent karta hai |
| NULL allowed nahi | NULL handling MySQL mein alag rules ke according hoti hai |
| Table mein one primary key constraint | Multiple UNIQUE constraints ho sakte hain |

---

# 5️⃣ ✅ CHECK

## 📌 Meaning

**CHECK** constraint kisi column ke data par **condition** apply karta hai.

Agar value condition satisfy nahi karti, to database us value ko reject kar sakta hai.

### 💡 Example

Age 18 ya usse zyada honi chahiye:

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Age INT CHECK (Age >= 18)
);
```

Yahaan:

```text
Age = 20  → ✅ Allowed
Age = 18  → ✅ Allowed
Age = 15  → ❌ Not allowed
```

### ⭐ Real-Life Examples

```sql
CHECK (Marks >= 0)
```

```sql
CHECK (Marks <= 100)
```

```sql
CHECK (Age >= 18)
```

> 💡 **Note:** CHECK constraint ka exact behavior MySQL version aur configuration par depend kar sakta hai; modern MySQL versions is constraint ko enforce karte hain.

---

# 6️⃣ ⚙️ DEFAULT

## 📌 Meaning

**DEFAULT** constraint kisi column ke liye ek **default value** set karta hai.

Agar INSERT ke time value nahi di jaati, to default value use ho sakti hai.

### 💡 Example

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    City VARCHAR(30) DEFAULT 'Jaunpur'
);
```

Agar city provide nahi ki:

```sql
INSERT INTO Student (Student_ID, Name)
VALUES (101, 'Kajal');
```

To `City` ki default value:

```text
Jaunpur
```

ho sakti hai.

---

# 🧩 Multiple Constraints Together

Ek column par multiple constraints bhi apply kiye ja sakte hain.

### 🔹 Example

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    Age INT CHECK (Age >= 18),
    City VARCHAR(30) DEFAULT 'Jaunpur'
);
```

Yahaan:

| Column | Constraint |
|---|---|
| `Student_ID` | PRIMARY KEY |
| `Name` | NOT NULL |
| `Email` | UNIQUE |
| `Age` | CHECK |
| `City` | DEFAULT |

---

# 🏷️ Named Constraints

Constraint ko ek specific **name** bhi diya ja sakta hai.

### 🔹 Example

```sql
CREATE TABLE Student (
    Student_ID INT,
    Age INT,
    CONSTRAINT pk_student PRIMARY KEY (Student_ID),
    CONSTRAINT chk_age CHECK (Age >= 18)
);
```

Yahaan:

- `pk_student` → Primary Key constraint ka name
- `chk_age` → Check constraint ka name

> 💡 Named constraints ko manage karna easier ho sakta hai, especially larger databases mein.

---

# 🔧 ALTER TABLE se Constraint Add Karna

Existing table mein bhi kuch constraints add kiye ja sakte hain.

### 🔹 UNIQUE Add

```sql
ALTER TABLE Student
ADD CONSTRAINT uq_email UNIQUE (Email);
```

### 🔹 FOREIGN KEY Add

```sql
ALTER TABLE Marks
ADD CONSTRAINT fk_student
FOREIGN KEY (Student_ID)
REFERENCES Student(Student_ID);
```

### 🔹 CHECK Add

```sql
ALTER TABLE Student
ADD CONSTRAINT chk_age
CHECK (Age >= 18);
```

---

# ❌ Constraint Remove Karna

### 🔹 UNIQUE Constraint Remove

```sql
ALTER TABLE Student
DROP INDEX uq_email;
```

### 🔹 FOREIGN KEY Remove

```sql
ALTER TABLE Marks
DROP FOREIGN KEY fk_student;
```

> 💡 Constraint remove karne ka syntax constraint ke type ke according different ho sakta hai.

---

# 🏫 🎯 Real-Life Example

Suppose ek college database mein `Student` table hai:

```text
Student_ID
Name
Email
Age
City
```

Rules:

```text
Student_ID → Unique identity
Name       → Required
Email      → Duplicate nahi
Age        → 18 or above
City       → Value missing ho to default city
```

In rules ko database mein constraints ke through implement kiya ja sakta hai.

---

# 📊 Constraint Summary

| 🔒 Constraint | 🎯 Main Purpose |
|---|---|
| **PRIMARY KEY** | Unique identification |
| **FOREIGN KEY** | Table relationship |
| **NOT NULL** | NULL value prevent |
| **UNIQUE** | Duplicate values prevent |
| **CHECK** | Condition enforce |
| **DEFAULT** | Default value provide |

---

# 🔍 PRIMARY KEY vs FOREIGN KEY

| Feature | PRIMARY KEY | FOREIGN KEY |
|---|---|---|
| Purpose | Record identify karna | Relationship banana |
| Duplicate | ❌ Not allowed | Allowed ho sakta hai |
| NULL | ❌ Not allowed | NULL allowed ho sakta hai, depending on definition |
| Reference | Usually kisi ko reference nahi karta | Other table ki key ko reference karta hai |

---

# 🔍 PRIMARY KEY vs UNIQUE

| Feature | PRIMARY KEY | UNIQUE |
|---|---|---|
| Duplicate | ❌ Not allowed | ❌ Not allowed |
| NULL | ❌ Not allowed | MySQL mein NULL handling alag ho sakti hai |
| Number per table | One PRIMARY KEY constraint | Multiple UNIQUE constraints possible |
| Main purpose | Unique identification | Uniqueness enforce karna |

---

# ⚠️ Constraint Violation

Agar data kisi constraint ke rule ko follow nahi karta, to **constraint violation** ho sakta hai.

### Example

Agar:

```sql
Age INT CHECK (Age >= 18)
```

aur invalid age insert ki:

```sql
INSERT INTO Student (Student_ID, Name, Age)
VALUES (101, 'Kajal', 15);
```

To condition satisfy nahi hogi aur MySQL modern versions mein is value ko reject kar sakta hai.

---

# 🌟 Advantages of Constraints

- ✅ Data accuracy improve hoti hai.
- ✅ Invalid data prevent hota hai.
- ✅ Duplicate data control hota hai.
- ✅ Data integrity maintain hoti hai.
- ✅ Tables ke relationships maintain hote hain.
- ✅ Database more reliable banta hai.
- ✅ Application mein data validation ka burden kam ho sakta hai.

---

# 📝 🎓 Exam Point of View

### Q1. What is a Constraint?

**Answer:**  
A constraint is a rule applied to a table or column to control the data that can be stored in a database. It helps maintain data accuracy and integrity.

---

### Q2. Name the types of constraints in MySQL.

**Answer:**

1. PRIMARY KEY
2. FOREIGN KEY
3. NOT NULL
4. UNIQUE
5. CHECK
6. DEFAULT

---

### Q3. What is Primary Key?

**Answer:**  
A Primary Key is a column or combination of columns that uniquely identifies each record in a table. It cannot contain duplicate or NULL values.

---

### Q4. What is Foreign Key?

**Answer:**  
A Foreign Key is a column that references a key in another table. It is used to establish a relationship between tables and maintain referential integrity.

---

### Q5. What is NOT NULL constraint?

**Answer:**  
NOT NULL constraint prevents a column from storing NULL values.

---

### Q6. What is UNIQUE constraint?

**Answer:**  
UNIQUE constraint prevents duplicate values from being stored in a column.

---

### Q7. What is CHECK constraint?

**Answer:**  
CHECK constraint applies a condition to the data stored in a column.

**Example:**

```sql
Age INT CHECK (Age >= 18)
```

---

### Q8. What is DEFAULT constraint?

**Answer:**  
DEFAULT constraint provides a predefined value when no value is supplied for a column during insertion.

---

# 🧠 ⭐ Quick Revision

```text
CONSTRAINT = Database ka Rule

PRIMARY KEY → Unique identity 🔑
FOREIGN KEY → Relationship 🔗
NOT NULL    → Empty/NULL value nahi 🚫
UNIQUE      → Duplicate nahi 🆔
CHECK       → Condition ✅
DEFAULT     → Default value ⚙️
```

> 💡 **Easy Trick:**  
> **P-F-N-U-C-D**  
> **Primary → Foreign → Not Null → Unique → Check → Default**
