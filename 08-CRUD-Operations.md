# 🛠️ **08 — CRUD OPERATIONS**

> 💡 **CRUD** database mein data ke saath kiye jaane wale **4 basic operations** ko represent karta hai.

---

## 📌 CRUD ka Full Form

| 🔤 Letter | 📝 Operation | 💡 Meaning |
|---|---|---|
| **C** | Create | Naya data add karna |
| **R** | Read | Data ko dekhna/retrieve karna |
| **U** | Update | Existing data ko change karna |
| **D** | Delete | Data ko remove karna |

### 🧠 Easy Trick

> **C → Create → Add**  
> **R → Read → Show**  
> **U → Update → Change**  
> **D → Delete → Remove**

---

# 1️⃣ 🟢 CREATE

## 📌 Meaning

**Create** ka matlab database/table mein **naya record add karna** hai.

MySQL mein existing table mein data add karne ke liye generally **INSERT** statement use hota hai.

### 🔹 Syntax

```sql
INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);
```

### 🔹 Example

```sql
INSERT INTO Student (id, name, course)
VALUES (101, 'Kajal', 'CSE');
```

Yahaan ek **new student record** add kiya gaya hai.

> 💡 **Note:** `INSERT` existing table mein new rows add karne ke liye use hota hai.

---

# 2️⃣ 🔵 READ

## 📌 Meaning

**Read** ka matlab database mein stored data ko **retrieve ya display** karna hai.

MySQL mein iske liye **SELECT** statement use hota hai.

### 🔹 Syntax

```sql
SELECT column1, column2
FROM table_name;
```

### 🔹 Example

```sql
SELECT name, course
FROM Student;
```

Ye `Student` table se **name aur course** display karega.

### 🔹 Saara Data Dekhna

```sql
SELECT *
FROM Student;
```

`*` ka matlab hai **all columns**.

---

# 3️⃣ 🟡 UPDATE

## 📌 Meaning

**Update** ka matlab existing record ke kisi data ko **change/modify** karna hai.

MySQL mein **UPDATE** statement use hota hai.

### 🔹 Syntax

```sql
UPDATE table_name
SET column_name = new_value
WHERE condition;
```

### 🔹 Example

```sql
UPDATE Student
SET course = 'IT'
WHERE id = 101;
```

Is query mein `id = 101` wale student ka course **CSE se IT** ho jayega.

> ⚠️ **Important:** `UPDATE` ke saath `WHERE` condition carefully use karni chahiye.  
> `WHERE` na dene par multiple/all records update ho sakte hain.

---

# 4️⃣ 🔴 DELETE

## 📌 Meaning

**Delete** ka matlab table se existing record ko **remove** karna hai.

MySQL mein **DELETE** statement use hota hai.

### 🔹 Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

### 🔹 Example

```sql
DELETE FROM Student
WHERE id = 101;
```

Isse `id = 101` wala record delete ho jayega.

> ⚠️ **Important:** `DELETE` ke saath `WHERE` condition carefully use karein.

---

# 📊 CRUD ka Complete Overview

| CRUD | Operation | SQL Statement | Work |
|---|---|---|---|
| 🟢 C | Create | `INSERT` | Data add |
| 🔵 R | Read | `SELECT` | Data retrieve |
| 🟡 U | Update | `UPDATE` | Data change |
| 🔴 D | Delete | `DELETE` | Data remove |

---

# 🏫 🎯 Real-Life Example

Suppose college ke paas **Student Database** hai.

### 🟢 Create
Naya student admission leta hai.

```sql
INSERT INTO Student (id, name, course)
VALUES (105, 'Rahul', 'CSE');
```

### 🔵 Read
Teacher student information check karta hai.

```sql
SELECT *
FROM Student;
```

### 🟡 Update
Student ka course change hota hai.

```sql
UPDATE Student
SET course = 'IT'
WHERE id = 105;
```

### 🔴 Delete
Student ka record database se remove karna ho.

```sql
DELETE FROM Student
WHERE id = 105;
```

---

# 🔄 CRUD Workflow

```text
        DATABASE
           │
           ▼
    ┌──────────────┐
    │    CREATE    │
    │  Add Record  │
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │     READ     │
    │ View Record  │
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │    UPDATE    │
    │ Change Data  │
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │    DELETE    │
    │ Remove Data  │
    └──────────────┘
```

---

# 🧪 💻 Practical CRUD Example

Maan lo `Employee` table mein employee information store hai.

### Step 1 — New Record Add

```sql
INSERT INTO Employee (id, name, salary)
VALUES (1, 'Aman', 25000);
```

### Step 2 — Record Read

```sql
SELECT *
FROM Employee;
```

### Step 3 — Salary Update

```sql
UPDATE Employee
SET salary = 30000
WHERE id = 1;
```

### Step 4 — Record Delete

```sql
DELETE FROM Employee
WHERE id = 1;
```

---

# 📌 CRUD mein Use Hone Wale Main SQL Commands

| Command | CRUD Operation |
|---|---|
| `INSERT` | Create |
| `SELECT` | Read |
| `UPDATE` | Update |
| `DELETE` | Delete |

> 💡 **Yaad rakhein:** CRUD ek concept hai, aur SQL mein is concept ko perform karne ke liye different statements use kiye jaate hain.

---

# ⚠️ Important Points

1. **CRUD** ka full form Create, Read, Update, Delete hai.
2. **INSERT** ka use new records add karne ke liye hota hai.
3. **SELECT** ka use data retrieve karne ke liye hota hai.
4. **UPDATE** existing data modify karta hai.
5. **DELETE** records remove karta hai.
6. `UPDATE` aur `DELETE` mein `WHERE` condition bahut important hoti hai.
7. CRUD operations database applications ka basic part hain.
8. CRUD operations ko web applications ke **backend** ke saath bhi use kiya ja sakta hai.

---

# 📝 🎓 Exam Point of View

### Q1. What is CRUD?

**Answer:**  
CRUD stands for **Create, Read, Update and Delete**. These are four basic operations used to manage data in a database.

---

### Q2. What is Create operation?

**Answer:**  
Create operation is used to add new records into a database table. In SQL, the `INSERT` statement is commonly used for this operation.

---

### Q3. What is Read operation?

**Answer:**  
Read operation is used to retrieve or display data from a database. In SQL, the `SELECT` statement is used for reading data.

---

### Q4. What is Update operation?

**Answer:**  
Update operation is used to modify existing data in a database table. In SQL, the `UPDATE` statement is used.

---

### Q5. What is Delete operation?

**Answer:**  
Delete operation is used to remove existing records from a database table. In SQL, the `DELETE` statement is used.

---

### Q6. Write the four CRUD operations with SQL commands.

**Answer:**

| Operation | SQL Command |
|---|---|
| Create | `INSERT` |
| Read | `SELECT` |
| Update | `UPDATE` |
| Delete | `DELETE` |

---

# 🧠 ⭐ Quick Revision

```text
CRUD = Create + Read + Update + Delete

C → INSERT → Add data
R → SELECT → View data
U → UPDATE → Change data
D → DELETE → Remove data
```

> 💡 **One-Line Trick:**  
> **CRUD = Add → Show → Change → Remove**
