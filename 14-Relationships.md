# 🔗 **14 — RELATIONSHIPS IN MYSQL**

---

## 📌 1. What is a Relationship?

Database me **Relationship** ka matlab hai do ya do se zyada tables ke data ke beech connection.

### 🧠 Simple Hinglish

Jab database ki different tables ek-doosre se logically connected hoti hain, to unke beech **Relationship** hota hai.

### 🎯 Example

Ek college database me:

- **Student** table me student ki information hoti hai.
- **Course** table me course ki information hoti hai.

Student aur Course ke beech connection ho sakta hai.

```text
Student
   ↓
Course
```

> 💡 **Easy Definition:**  
> Relationship = **Tables ke beech logical connection**

---

# 📊 2. Why are Relationships Used?

Relationships ka use database me:

- Related data ko connect karne ke liye
- Data ko properly organize karne ke liye
- Duplicate data ko reduce karne ke liye
- Tables ke beech connection maintain karne ke liye
- Database ko structured banane ke liye

---

# 🔢 3. Types of Relationships

Database me mainly **3 types of relationships** important hain:

1. **One-to-One (1:1)**
2. **One-to-Many (1:M)**
3. **Many-to-Many (M:N)**

---

# 1️⃣ 4. One-to-One Relationship (1:1)

### 📌 Definition

Jab table A ka **one record** table B ke **only one record** se related ho, aur table B ka bhi one record table A ke only one record se related ho, to ise **One-to-One Relationship** kehte hain.

### 🧠 Simple Hinglish

**One record → One record**

### 🎯 Real-Life Example

Ek person ka ek passport ho sakta hai.

```text
Person
  1
  │
  │
  1
Passport
```

### 📋 Example

**Person Table**

| Person_ID | Name |
|---|---|
| 101 | Ravi |
| 102 | Aman |

**Passport Table**

| Passport_ID | Person_ID |
|---|---|
| P101 | 101 |
| P102 | 102 |

Yahan ek person ek passport se related hai.

### 🌍 Other Examples

- Person ↔ Passport
- Employee ↔ Employee_ID_Card
- Student ↔ Student_Profile

---

# 2️⃣ 5. One-to-Many Relationship (1:M)

### 📌 Definition

Jab table A ka **one record** table B ke **multiple records** se related ho sakta hai, to ise **One-to-Many Relationship** kehte hain.

### 🧠 Simple Hinglish

**One record → Many records**

### 🎯 Real-Life Example

Ek department me multiple employees ho sakte hain.

```text
Department
    1
    │
    ├──────── Employee
    ├──────── Employee
    └──────── Employee
                 M
```

### 📋 Example

**Department Table**

| Department_ID | Department_Name |
|---|---|
| 1 | CSE |
| 2 | IT |

**Employee Table**

| Employee_ID | Name | Department_ID |
|---|---|---|
| 101 | Ravi | 1 |
| 102 | Aman | 1 |
| 103 | Neha | 1 |
| 104 | Pooja | 2 |

Yahan:

```text
CSE Department
      ↓
Ravi
Aman
Neha
```

Ek department ke multiple employees hain.

### 🌍 Other Examples

- Department → Employees
- Customer → Orders
- Teacher → Students
- Category → Products

---

# 3️⃣ 6. Many-to-Many Relationship (M:N)

### 📌 Definition

Jab table A ka **multiple records** table B ke **multiple records** se related ho sakte hain, to ise **Many-to-Many Relationship** kehte hain.

### 🧠 Simple Hinglish

**Many records → Many records**

### 🎯 Real-Life Example

Ek student multiple courses kar sakta hai aur ek course ko multiple students kar sakte hain.

```text
Students              Courses

Student 1 ─────────── Course A
Student 1 ─────────── Course B
Student 2 ─────────── Course A
Student 2 ─────────── Course C
```

### 📌 Problem

Directly two tables me Many-to-Many relationship manage karna difficult hota hai.

Isliye ek **third table** create ki jaati hai.

Is third table ko:

- **Junction Table**
- **Bridge Table**
- **Associative Table**

kaha ja sakta hai.

---

# 🧩 7. Junction Table

### 📌 Definition

Many-to-Many relationship ko manage karne ke liye jo intermediate table use hoti hai, use **Junction Table** kehte hain.

### 📋 Example

**Student Table**

| Student_ID | Name |
|---|---|
| 101 | Ravi |
| 102 | Aman |

**Course Table**

| Course_ID | Course_Name |
|---|---|
| 1 | C Programming |
| 2 | MySQL |
| 3 | Java |

Ab relationship ke liye:

**Student_Course Table**

| Student_ID | Course_ID |
|---|---|
| 101 | 1 |
| 101 | 2 |
| 102 | 1 |
| 102 | 3 |

### 🔗 Relationship

```text
Student
   1
   │
   │
   M
Student_Course
   M
   │
   │
   1
Course
```

Is tarah Many-to-Many relationship ko **two One-to-Many relationships** me represent kiya ja sakta hai.

---

# 🏗️ 8. Creating Tables for a Relationship

### Student Table

```sql
CREATE TABLE Student (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50)
);
```

### Course Table

```sql
CREATE TABLE Course (
    Course_ID INT PRIMARY KEY,
    Course_Name VARCHAR(50)
);
```

### Junction Table

```sql
CREATE TABLE Student_Course (
    Student_ID INT,
    Course_ID INT,
    PRIMARY KEY (Student_ID, Course_ID)
);
```

> 💡 Yahan `Student_Course` table Student aur Course ke relationship ko represent karti hai.

---

# 🔢 9. Cardinality

### 📌 Definition

**Cardinality** batati hai ki ek table ke kitne records doosre table ke kitne records se related ho sakte hain.

### 🧠 Simple Hinglish

Cardinality ka simple meaning:

**"Kitne records ka kitne records se relation hai?"**

### Types

| Cardinality | Meaning |
|---|---|
| **1:1** | One → One |
| **1:M** | One → Many |
| **M:N** | Many → Many |

### Example

```text
1 : 1  → Person : Passport

1 : M  → Department : Employee

M : N  → Student : Course
```

---

# 🔄 10. Relationship Direction

Relationship
