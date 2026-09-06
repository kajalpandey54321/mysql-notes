# 📊 **11 — GROUP BY AND HAVING**

> 💡 **GROUP BY** ka use same values wale records ko groups mein divide karne ke liye hota hai, jabki **HAVING** ka use un groups ko condition ke basis par filter karne ke liye hota hai.

---

# 📌 1. GROUP BY Kya Hai?

### 📝 Definition

`GROUP BY` clause is used to group rows that have the same values in one or more columns.

### 💡 Hinglish Explanation

Maan lo Student table mein different courses ke students hain:

| ID | Name | Course | Marks |
|---:|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | IT | 72 |
| 103 | Aman | CSE | 91 |
| 104 | Priya | ECE | 65 |
| 105 | Neha | IT | 80 |

Agar humein **course-wise data** chahiye, to hum `GROUP BY Course` use kar sakte hain.

```sql
SELECT Course
FROM Student
GROUP BY Course;
```

Result mein har course ka group milega:

```text
CSE
IT
ECE
```

---

# 🎯 2. GROUP BY ka Main Purpose

`GROUP BY` ka use mainly:

- ✅ Similar values ko group karne ke liye
- ✅ Category-wise analysis ke liye
- ✅ Aggregate functions ke saath summary banane ke liye
- ✅ Course-wise, city-wise, department-wise data analyse karne ke liye

---

# 🔗 3. GROUP BY with Aggregate Functions

`GROUP BY` ka sabse common use aggregate functions ke saath hota hai.

Common aggregate functions:

```text
COUNT()
SUM()
AVG()
MAX()
MIN()
```

---

# 🔢 4. COUNT() with GROUP BY

### 🎯 Question:

Har course mein kitne students hain?

### ✅ Query:

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course;
```

### 📊 Example Result

| Course | Total_Students |
|---|---:|
| CSE | 2 |
| IT | 2 |
| ECE | 1 |

### 💡 Explanation

- `GROUP BY Course` → students ko course-wise group karta hai.
- `COUNT(*)` → har group ke students count karta hai.

---

# ➕ 5. SUM() with GROUP BY

### 🎯 Question:

Har course ke students ke marks ka total find karna hai.

```sql
SELECT Course, SUM(Marks) AS Total_Marks
FROM Student
GROUP BY Course;
```

### Example

CSE students:

```text
85 + 91 = 176
```

---

# 📊 6. AVG() with GROUP BY

### 🎯 Question:

Har course ka average marks find karna hai.

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course;
```

### Example Result

| Course | Average_Marks |
|---|---:|
| CSE | 88.00 |
| IT | 76.00 |
| ECE | 65.00 |

> 💡 Isse humein **course-wise average performance** pata chalti hai.

---

# 🔝 7. MAX() with GROUP BY

Har course ke highest marks:

```sql
SELECT Course, MAX(Marks) AS Highest_Marks
FROM Student
GROUP BY Course;
```

Example:

| Course | Highest_Marks |
|---|---:|
| CSE | 91 |
| IT | 80 |
| ECE | 65 |

---

# 🔽 8. MIN() with GROUP BY

Har course ke lowest marks:

```sql
SELECT Course, MIN(Marks) AS Lowest_Marks
FROM Student
GROUP BY Course;
```

---

# 🏙️ 9. City-wise Grouping

GROUP BY sirf Course ke liye nahi hota.

Suppose:

| Name | City |
|---|---|
| Kajal | Jaunpur |
| Rahul | Varanasi |
| Aman | Jaunpur |
| Priya | Lucknow |
| Neha | Varanasi |

### 🎯 City-wise students count:

```sql
SELECT City, COUNT(*) AS Total_Students
FROM Student
GROUP BY City;
```

Isse har city ke students ki count mil jayegi.

---

# 📌 10. Multiple Columns ke Saath GROUP BY

Ek se zyada columns ke according bhi grouping kar sakte hain.

### 🔹 Syntax

```sql
SELECT column1, column2, COUNT(*)
FROM table_name
GROUP BY column1, column2;
```

### 🔹 Example

```sql
SELECT Course, City, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course, City;
```

Yahaan students ko:

```text
Course + City
```

ke combination ke according groups mein divide kiya jayega.

---

# 🔥 11. HAVING Clause

## 📌 Definition

`HAVING` clause ka use **GROUP BY se banaye gaye groups ko filter** karne ke liye hota hai.

### 💡 Simple Hinglish

```text
WHERE  → Individual rows ko filter karta hai

HAVING → Groups ko filter karta hai
```

---

# 🎯 12. HAVING ka Example

### Question:

Sirf wahi courses show karo jisme **2 se zyada students** hain.

### ✅ Query:

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course
HAVING COUNT(*) > 2;
```

Yahaan:

1. Students ko `Course` ke according group kiya.
2. Har course ke students count kiye.
3. Sirf `COUNT(*) > 2` wale groups show kiye.

---

# 📊 13. GROUP BY + HAVING with AVG()

### 🎯 Question:

Sirf un courses ko show karo jinka average marks **75 se zyada** hai.

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course
HAVING AVG(Marks) > 75;
```

> 💡 `HAVING` aggregate result par condition lagane ke liye especially useful hai.

---

# 🔝 14. GROUP BY + HAVING with MAX()

### 🎯 Question:

Sirf un courses ko show karo jinka highest marks **80 se greater** hai.

```sql
SELECT Course, MAX(Marks) AS Highest_Marks
FROM Student
GROUP BY Course
HAVING MAX(Marks) > 80;
```

---

# 🔢 15. GROUP BY + WHERE

`WHERE` aur `GROUP BY` ko ek saath use kiya ja sakta hai.

### 🎯 Example

Sirf CSE aur IT students ko consider karke course-wise count:

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
WHERE Course IN ('CSE', 'IT')
GROUP BY Course;
```

### 💡 Working

```text
Student Table
      ↓
WHERE
      ↓
Required rows select
      ↓
GROUP BY
      ↓
Groups create
      ↓
COUNT()
      ↓
Result
```

---

# 🔥 16. WHERE vs HAVING

Ye exam ka **very important difference** hai.

| WHERE | HAVING |
|---|---|
| Rows ko filter karta hai | Groups ko filter karta hai |
| GROUP BY se pehle logically apply hota hai | GROUP BY ke baad logically apply hota hai |
| Individual records par condition | Group/aggregate result par condition |
| Aggregate result ko directly filter karne ke liye generally use nahi hota | Aggregate functions ke saath commonly use hota hai |

### 🧠 Easy Trick

> **WHERE = Rows**  
> **HAVING = Groups**

---

# 🔄 17. GROUP BY Query ka Logical Flow

Ek common query:

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
WHERE Marks >= 40
GROUP BY Course
HAVING AVG(Marks) > 70
ORDER BY Average_Marks DESC;
```

Iska logical flow:

```text
FROM
 ↓
WHERE
 ↓
GROUP BY
 ↓
HAVING
 ↓
SELECT
 ↓
ORDER BY
```

> 💡 Ye **logical processing order** hai. Query likhte waqt SQL syntax mein `SELECT` pehle likha jata hai.

---

# 📋 18. Complete Example

Suppose Student table:

| ID | Name | Course | Marks |
|---:|---|---|---:|
| 101 | Kajal | CSE | 85 |
| 102 | Rahul | IT | 72 |
| 103 | Aman | CSE | 91 |
| 104 | Priya | ECE | 65 |
| 105 | Neha | IT | 80 |
| 106 | Ravi | CSE | 76 |

### 🎯 Course-wise student count

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course;
```

### 🎯 Course-wise average marks

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course;
```

### 🎯 Average marks 75 se zyada wale courses

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course
HAVING AVG(Marks) > 75;
```

---

# 🧩 19. GROUP BY + HAVING + ORDER BY

Course-wise average marks ko descending order mein arrange karna:

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course
HAVING AVG(Marks) > 60
ORDER BY Average_Marks DESC;
```

### 💡 Meaning

- `GROUP BY` → Course-wise groups
- `AVG()` → Average marks
- `HAVING` → Average > 60
- `ORDER BY` → Highest average first

---

# 🧠 20. GROUP BY ko Easily Samjho

Maan lo students hain:

```text
CSE → Kajal
CSE → Aman
CSE → Ravi

IT → Rahul
IT → Neha

ECE → Priya
```

`GROUP BY Course` ke baad:

```text
CSE → Kajal, Aman, Ravi
IT  → Rahul, Neha
ECE → Priya
```

Ab `COUNT()` lagane par:

```text
CSE → 3
IT  → 2
ECE → 1
```

Aur agar:

```sql
HAVING COUNT(*) > 2
```

lagaya:

```text
CSE → 3
```

Sirf CSE group bachega.

---

# 📌 21. Important Rules

### Rule 1️⃣

`GROUP BY` ke saath selected non-aggregate columns generally `GROUP BY` mein included hone chahiye.

Example:

```sql
SELECT Course, COUNT(*)
FROM Student
GROUP BY Course;
```

### Rule 2️⃣

Aggregate result ko filter karne ke liye `HAVING` useful hai.

```sql
HAVING COUNT(*) > 2
```

### Rule 3️⃣

Individual rows ko filter karne ke liye `WHERE` use karein.

```sql
WHERE Marks >= 60
```

---

# 📊 22. GROUP BY vs HAVING

| GROUP BY | HAVING |
|---|---|
| Rows ko groups mein divide karta hai | Groups ko filter karta hai |
| Similar values ko combine karta hai | Condition ke according groups select karta hai |
| Aggregate functions ke saath commonly use hota hai | Aggregate results ke saath commonly use hota hai |
| Example: `GROUP BY Course` | Example: `HAVING COUNT(*) > 2` |

---

# 🎯 23. Real-Life Applications

GROUP BY aur HAVING ka use:

- 🏫 Course-wise students count
- 📚 Subject-wise marks analysis
- 🏢 Department-wise employees
- 🏙️ City-wise customers
- 🛒 Category-wise products
- 💰 Department-wise salary analysis
- 📊 Sales category analysis

---

# ⚠️ Important Points

1. `GROUP BY` similar values ko groups mein divide karta hai.
2. `GROUP BY` aggregate functions ke saath commonly use hota hai.
3. `HAVING` groups ko filter karta hai.
4. `WHERE` rows ko filter karta hai.
5. `HAVING` aggregate conditions ke liye useful hai.
6. `COUNT()` se group-wise records count kar sakte hain.
7. `SUM()` se group-wise total calculate kar sakte hain.
8. `AVG()` se group-wise average calculate kar sakte hain.
9. `MAX()` se group-wise highest value find kar sakte hain.
10. `MIN()` se group-wise lowest value find kar sakte hain.
11. Multiple columns ko `GROUP BY` mein use kiya ja sakta hai.
12. `ORDER BY` ke saath grouped result ko sort bhi kar sakte hain.

---

# 📝 🎓 Exam Point of View

### Q1. What is GROUP BY?

**Answer:**  
`GROUP BY` is an SQL clause used to group rows having the same values in one or more columns. It is commonly used with aggregate functions.

---

### Q2. What is HAVING?

**Answer:**  
`HAVING` is an SQL clause used to filter groups created by the `GROUP BY` clause.

---

### Q3. Difference between WHERE and HAVING.

**Answer:**

| WHERE | HAVING |
|---|---|
| Filters individual rows | Filters groups |
| Used before grouping logically | Used after grouping logically |
| Commonly used with normal column conditions | Commonly used with aggregate conditions |

---

### Q4. Write a query to count students course-wise.

**Answer:**

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course;
```

---

### Q5. Write a query to display courses having more than 2 students.

**Answer:**

```sql
SELECT Course, COUNT(*) AS Total_Students
FROM Student
GROUP BY Course
HAVING COUNT(*) > 2;
```

---

### Q6. Write a query to find average marks course-wise.

**Answer:**

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course;
```

---

### Q7. Write a query to display courses whose average marks are greater than 75.

**Answer:**

```sql
SELECT Course, AVG(Marks) AS Average_Marks
FROM Student
GROUP BY Course
HAVING AVG(Marks) > 75;
```

---

# 🧠 ⭐ Quick Revision

```text
GROUP BY
    ↓
Same values ko groups mein divide karta hai

COUNT() → Group mein kitne records?
SUM()   → Group ka total?
AVG()   → Group ka average?
MAX()   → Group ki highest value?
MIN()   → Group ki lowest value?

HAVING
    ↓
Groups ko condition ke basis par filter karta hai
```

### 🔥 One-Line Trick

> **WHERE → Rows ko Filter**  
> **GROUP BY → Rows ko Group**  
> **HAVING → Groups ko Filter**  
> **ORDER BY → Result ko Sort**
