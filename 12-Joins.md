# 🔗 **12 — JOINS IN MYSQL**

> 💡 **JOIN** ka use do ya do se zyada tables ke related data ko combine karke ek result mein display karne ke liye hota hai.

---

# 📌 1. What is JOIN?

### 📝 Definition

A **JOIN** is an SQL operation used to combine rows from two or more tables based on a related column between them.

### 💡 Hinglish Explanation

Database mein information ko alag-alag tables mein store kiya ja sakta hai.

Example:

**Student Table**

| Student_ID | Name | Course_ID |
|---:|---|---:|
| 101 | Kajal | 1 |
| 102 | Rahul | 2 |
| 103 | Aman | 1 |

**Course Table**

| Course_ID | Course_Name |
|---:|---|
| 1 | CSE |
| 2 | IT |

Agar humein student ka **Name + Course_Name** ek saath chahiye, to dono tables ko JOIN kar sakte hain.

---

# 🎯 2. Why Do We Use JOIN?

JOIN ka use:

- ✅ Multiple tables se related data retrieve karne ke liye
- ✅ Tables ke relationships ka use karne ke liye
- ✅ Data ko ek combined result mein display karne ke liye
- ✅ Normalized database se information obtain karne ke liye

---

# 📚 3. Types of JOIN

MySQL mein commonly ye JOIN types use hote hain:

| 🔢 JOIN | 📝 Purpose |
|---|---|
| **INNER JOIN** | Dono tables mein matching records |
| **LEFT JOIN** | Left table ke all records + matching right records |
| **RIGHT JOIN** | Right table ke all records + matching left records |
| **CROSS JOIN** | Dono tables ke all possible combinations |
| **SELF JOIN** | Same table ko khud se join karna |

> 💡 **Note:** `FULL OUTER JOIN` MySQL mein directly supported JOIN syntax nahi hai. Iska result generally `LEFT JOIN` + `RIGHT JOIN` ko `UNION` ke through combine karke obtain kiya ja sakta hai.

---

# 1️⃣ 🟢 INNER JOIN

## 📌 Meaning

`INNER JOIN` sirf un records ko return karta hai jinke beech **matching value** available hoti hai.

### 🔹 Syntax

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 🔹 Example

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
INNER JOIN Course
ON Student.Course_ID = Course.Course_ID;
```

### 📊 Result

| Name | Course_Name |
|---|---|
| Kajal | CSE |
| Rahul | IT |
| Aman | CSE |

### 🧠 Easy Way

```text
INNER JOIN
     ↓
Only Matching Records
```

---

# 2️⃣ 🔵 LEFT JOIN

## 📌 Meaning

`LEFT JOIN` **left table ke saare records** return karta hai aur right table se sirf matching records leta hai.

Agar right table mein match nahi milta, to right-side columns mein `NULL` aa sakta hai.

### 🔹 Syntax

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

### 🔹 Example

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
LEFT JOIN Course
ON Student.Course_ID = Course.Course_ID;
```

### 🧠 Easy Way

```text
LEFT JOIN
     ↓
Left Table → All Records
Right Table → Matching Records
```

---

# 3️⃣ 🟠 RIGHT JOIN

## 📌 Meaning

`RIGHT JOIN` **right table ke saare records** return karta hai aur left table se matching records leta hai.

Agar left table mein match nahi milta, to left-side columns mein `NULL` aa sakta hai.

### 🔹 Example

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
RIGHT JOIN Course
ON Student.Course_ID = Course.Course_ID;
```

### 🧠 Easy Way

```text
RIGHT JOIN
      ↓
Right Table → All Records
Left Table → Matching Records
```

---

# 4️⃣ 🟣 CROSS JOIN

## 📌 Meaning

`CROSS JOIN` dono tables ki **har possible row combination** generate karta hai.

Agar:

```text
Table A → 3 rows
Table B → 2 rows
```

To result:

```text
3 × 2 = 6 rows
```

ho sakta hai.

### 🔹 Example

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
CROSS JOIN Course;
```

### 🧠 Easy Way

```text
Every row of A
       ×
Every row of B
```

> ⚠️ **Important:** CROSS JOIN large tables par bahut large result generate kar sakta hai.

---

# 5️⃣ 🟤 SELF JOIN

## 📌 Meaning

**SELF JOIN** mein ek table ko **usi table ke saath** join kiya jata hai.

Isme table ke different aliases use kiye jaate hain.

### 🎯 Example

Maan lo `Employee` table:

| Employee_ID | Employee_Name | Manager_ID |
|---:|---|---:|
| 1 | Aman | NULL |
| 2 | Rahul | 1 |
| 3 | Priya | 1 |

Yahaan `Manager_ID` bhi isi `Employee` table ke `Employee_ID` ko refer karta hai.

### 🔹 Query

```sql
SELECT
    E.Employee_Name AS Employee,
    M.Employee_Name AS Manager
FROM Employee E
LEFT JOIN Employee M
ON E.Manager_ID = M.Employee_ID;
```

### 💡 Explanation

- `E` → Employee table ka first alias
- `M` → Employee table ka second alias
- Same table ko do roles mein use kiya gaya hai.

---

# 📊 4. JOIN Types Comparison

| JOIN Type | Result |
|---|---|
| **INNER JOIN** | Only matching records |
| **LEFT JOIN** | Left ke all + right ke matching |
| **RIGHT JOIN** | Right ke all + left ke matching |
| **CROSS JOIN** | All possible combinations |
| **SELF JOIN** | Same table with itself |

---

# 🔑 5. JOIN Condition — ON

JOIN karte waqt related columns ko connect karne ke liye commonly `ON` clause use hota hai.

### Example

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
INNER JOIN Course
ON Student.Course_ID = Course.Course_ID;
```

Yahaan:

```text
Student.Course_ID
        =
Course.Course_ID
```

ke basis par tables connect ho rahe hain.

---

# 🏷️ 6. Table Aliases with JOIN

Long table names ko short karne ke liye **alias** use kar sakte hain.

### Without Alias

```sql
SELECT Student.Name, Course.Course_Name
FROM Student
INNER JOIN Course
ON Student.Course_ID = Course.Course_ID;
```

### With Alias

```sql
SELECT S.Name, C.Course_Name
FROM Student AS S
INNER JOIN Course AS C
ON S.Course_ID = C.Course_ID;
```

Yahaan:

```text
S → Student
C → Course
```

> 💡 Alias query ko short aur readable bana sakta hai.

---

# 🎯 7. JOIN with WHERE

JOIN ke result ko further filter bhi kar sakte hain.

### Example

Sirf CSE students:

```sql
SELECT S.Name, C.Course_Name
FROM Student AS S
INNER JOIN Course AS C
ON S.Course_ID = C.Course_ID
WHERE C.Course_Name = 'CSE';
```

### 💡 Working

```text
Student Table
      +
Course Table
      ↓
JOIN
      ↓
Matching Records
      ↓
WHERE
      ↓
Only CSE
```

---

# 🔢 8. JOIN with Multiple Tables

Kabhi-kabhi information **2 se zyada tables** mein stored hoti hai.

Example:

```text
Student
   ↓
Course
   ↓
Department
```

### 🔹 Query

```sql
SELECT
    S.Name,
    C.Course_Name,
    D.Department_Name
FROM Student AS S
INNER JOIN Course AS C
    ON S.Course_ID = C.Course_ID
INNER JOIN Department AS D
    ON C.Department_ID = D.Department_ID;
```

Yahaan 3 tables ka related data combine kiya gaya hai.

---

# 🧩 9. INNER JOIN vs LEFT JOIN

| INNER JOIN | LEFT JOIN |
|---|---|
| Sirf matching records | Left table ke all records |
| Non-matching left records nahi aate | Non-matching left records bhi aate hain |
| Matching data par focus | Left table ko complete preserve karta hai |

### 🧠 Easy Trick

```text
INNER → Match Only

LEFT → Left All + Match
```

---

# 🧩 10. LEFT JOIN vs RIGHT JOIN

| LEFT JOIN | RIGHT JOIN |
|---|---|
| Left table ke all records | Right table ke all records |
| Right se matching records | Left se matching records |
| Non-match right side par NULL | Non-match left side par NULL |

### 💡 Easy Trick

> **LEFT JOIN → Left ko priority**  
> **RIGHT JOIN → Right ko priority**

---

# 🏫 🎯 11. Real-Life Example

College database mein:

### Student Table

| Student_ID | Name | Course_ID |
|---:|---|---:|
| 101 | Kajal | 1 |
| 102 | Rahul | 2 |
| 103 | Aman | 1 |

### Course Table

| Course_ID | Course_Name |
|---:|---|
| 1 | CSE |
| 2 | IT |

Agar humein ye information chahiye:

```text
Student Name → Course Name
```

to INNER JOIN use kar sakte hain:

```sql
SELECT S.Name, C.Course_Name
FROM Student AS S
INNER JOIN Course AS C
ON S.Course_ID = C.Course_ID;
```

---

# 🔄 12. JOIN ka Basic Working

```text
Table 1
   │
   │ Related Column
   ↓
  JOIN
   ↑
   │ Related Column
   │
Table 2
   │
   ↓
Combined Result
```

Example:

```text
Student.Course_ID
       │
       │ JOIN
       ↓
Course.Course_ID
       │
       ↓
Student + Course Information
```

---

# ⚠️ 13. Important Points

1. JOIN ka use multiple tables ka related data combine karne ke liye hota hai.
2. `INNER JOIN` matching records return karta hai.
3. `LEFT JOIN` left table ke all records return karta hai.
4. `RIGHT JOIN` right table ke all records return karta hai.
5. `CROSS JOIN` all possible combinations create karta hai.
6. `SELF JOIN` same table ko khud se join karta hai.
7. JOIN condition commonly `ON` clause mein likhi jaati hai.
8. Table aliases query ko short aur readable bana sakte hain.
9. JOIN ke saath `WHERE`, `GROUP BY`, `HAVING` aur `ORDER BY` bhi use kiye ja sakte hain.
10. Multiple tables ko ek query mein join kiya ja sakta hai.
11. MySQL mein `FULL OUTER JOIN` ka direct syntax available nahi hai.

---

# 📝 🎓 Exam Point of View

### Q1. What is JOIN?

**Answer:**  
JOIN is an SQL operation used to combine related data from two or more tables based on a common or related column.

---

### Q2. Name the different types of JOIN.

**Answer:**

1. INNER JOIN
2. LEFT JOIN
3. RIGHT JOIN
4. CROSS JOIN
5. SELF JOIN

---

### Q3. What is INNER JOIN?

**Answer:**  
INNER JOIN returns only those records that have matching values in both tables.

---

### Q4. What is LEFT JOIN?

**Answer:**  
LEFT JOIN returns all records from the left table and matching records from the right table. If no match exists, NULL values may appear for the right-side columns.

---

### Q5. What is RIGHT JOIN?

**Answer:**  
RIGHT JOIN returns all records from the right table and matching records from the left table.

---

### Q6. What is CROSS JOIN?

**Answer:**  
CROSS JOIN returns the Cartesian product of two tables, meaning every row of the first table is combined with every row of the second table.

---

### Q7. What is SELF JOIN?

**Answer:**  
SELF JOIN is a join in which a table is joined with itself. It is useful when records within the same table are related to each other.

---

### Q8. Difference between INNER JOIN and LEFT JOIN.

**Answer:**

| INNER JOIN | LEFT JOIN |
|---|---|
| Only matching records | All left table records |
| Non-matching records excluded | Non-matching left records included |
| Focuses on matches | Preserves complete left table |

---

### Q9. Write an INNER JOIN query between Student and Course.

**Answer:**

```sql
SELECT S.Name, C.Course_Name
FROM Student AS S
INNER JOIN Course AS C
ON S.Course_ID = C.Course_ID;
```

---

# 🧠 ⭐ Quick Revision

```text
JOIN
 ↓
Multiple Tables ka Related Data Combine

INNER JOIN → Matching records
LEFT JOIN  → Left all + Right matching
RIGHT JOIN → Right all + Left matching
CROSS JOIN → All possible combinations
SELF JOIN  → Same table with itself

ON → Tables ko connect karne ki condition
AS → Table alias dene ke liye
```

> 💡 **One-Line Trick:**
>
> **INNER = Match**  
> **LEFT = Left All**  
> **RIGHT = Right All**  
> **CROSS = Everything with Everything**  
> **SELF = Same Table**
