# 🔍 **15 — SUBQUERIES IN MYSQL**

---

## 📌 1. What is a Subquery?

### 📖 Definition

A **Subquery** is a query written **inside another SQL query**.

A subquery is also called an **Inner Query** or **Nested Query**.

### 🧠 Simple Hinglish

Jab ek SQL query ke andar **dusri SQL query** likhi jaati hai, to andar wali query ko **Subquery** kehte hain.

```text
Main Query
    ↓
  Subquery
```

> 💡 **Easy Definition:**  
> **Query ke andar Query = Subquery**

---

## 🎯 2. Why are Subqueries Used?

Subqueries ka use tab hota hai jab hume pehle kisi query se information find karni ho aur us information ko **main query me use** karna ho.

### Common Uses

- Kisi value ko pehle find karna
- Us result ke basis par data retrieve karna
- Comparison karna
- Related records find karna
- Complex queries ko solve karna

---

## 🧩 3. Basic Structure of a Subquery

```sql
SELECT column_name
FROM table_name
WHERE column_name = (
    SELECT column_name
    FROM table_name
    WHERE condition
);
```

### 🧠 Structure Samjho

```text
Outer Query
     ↓
WHERE condition
     ↓
( Inner Query / Subquery )
```

Subquery generally **parentheses `( )`** ke andar likhi jaati hai.

---

# 📊 4. Example Table

Hum examples ke liye ye `Student` table maanenge:

| Student_ID | Name | Marks | City |
|---|---|---:|---|
| 101 | Ravi | 85 | Delhi |
| 102 | Aman | 72 | Jaunpur |
| 103 | Neha | 91 | Lucknow |
| 104 | Pooja | 65 | Delhi |
| 105 | Rahul | 78 | Jaunpur |

---

# ⭐ 5. Simple Subquery Example

### 🎯 Question

**Ravi ke marks ke equal marks wale students find karo.**

Pehle Ravi ke marks find karenge:

```sql
SELECT Marks
FROM Student
WHERE Name = 'Ravi';
```

Result:

```text
85
```

Ab isi result ko main query me use kar sakte hain:

```sql
SELECT Name, Marks
FROM Student
WHERE Marks = (
    SELECT Marks
    FROM Student
    WHERE Name = 'Ravi'
);
```

### 🧠 Working

```text
Subquery:
Ravi ke Marks → 85

        ↓

Main Query:
Marks = 85

        ↓

Matching Students
```

---

# 🔢 6. Types of Subqueries

Subqueries ko different ways me classify kiya ja sakta hai.

Important types:

1. **Single-Row Subquery**
2. **Multiple-Row Subquery**
3. **Multiple-Column Subquery**
4. **Correlated Subquery**
5. **Nested Subquery**

---

# 1️⃣ 7. Single-Row Subquery

### 📌 Definition

Jab subquery **sirf ek row/value** return karti hai, use **Single-Row Subquery** kehte hain.

### Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks > (
    SELECT Marks
    FROM Student
    WHERE Name = 'Aman'
);
```

Subquery Aman ke marks return karegi:

```text
72
```

Main query 72 se zyada marks wale students find karegi.

### Result

| Name | Marks |
|---|---:|
| Ravi | 85 |
| Neha | 91 |
| Rahul | 78 |

> 💡 Single-row subquery ke saath commonly `=`, `>`, `<`, `>=`, `<=` jaise comparison operators use kiye ja sakte hain.

---

# 2️⃣ 8. Multiple-Row Subquery

### 📌 Definition

Jab subquery **multiple rows/values** return karti hai, use **Multiple-Row Subquery** kehte hain.

Aise cases me `IN`, `ANY`, `ALL` jaise operators useful hote hain.

### Example

Suppose hume Jaunpur ke students ke marks ke equal marks wale students find karne hain.

```sql
SELECT Name, Marks
FROM Student
WHERE Marks IN (
    SELECT Marks
    FROM Student
    WHERE City = 'Jaunpur'
);
```

Subquery Jaunpur students ke marks return karegi:

```text
72
78
```

Main query in values ke matching students find karegi.

---

# 🔢 9. IN with Subquery

### 📌 Definition

`IN` check karta hai ki koi value subquery se returned values ki list me present hai ya nahi.

### Example

```sql
SELECT Name, City
FROM Student
WHERE Marks IN (
    SELECT Marks
    FROM Student
    WHERE City = 'Jaunpur'
);
```

### 🧠 Simple Hinglish

```text
Subquery → multiple marks
              ↓
Main Query → un marks ko match karegi
```

> 💡 `IN` multiple returned values ke saath useful hota hai.

---

# 🎯 10. ANY with Subquery

### 📌 Definition

`ANY` tab true hota hai jab comparison **subquery ke at least one result** ke saath true ho.

### Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks > ANY (
    SELECT Marks
    FROM Student
    WHERE City = 'Jaunpur'
);
```

Agar subquery results:

```text
72
78
```

hain, to condition ka matlab hoga:

```text
Marks > 72
OR
Marks > 78
```

> 💡 **ANY = At least one value**

---

# 🏆 11. ALL with Subquery

### 📌 Definition

`ALL` tab true hota hai jab comparison **subquery ke sabhi results** ke saath true ho.

### Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks > ALL (
    SELECT Marks
    FROM Student
    WHERE City = 'Jaunpur'
);
```

Agar subquery results:

```text
72
78
```

hain, to student ke marks ko **72 aur 78 dono se greater** hona chahiye.

> 💡 **ALL = Every value**

---

# 📊 12. Multiple-Column Subquery

### 📌 Definition

Jab subquery **ek se zyada columns** return karti hai, use Multiple-Column Subquery kaha ja sakta hai.

### Example

```sql
SELECT Name, Marks, City
FROM Student
WHERE (Marks, City) IN (
    SELECT Marks, City
    FROM Student
    WHERE Name = 'Ravi'
);
```

Yahan subquery:

```text
Marks
City
```

do columns return kar rahi hai.

> 💡 Multiple-column comparison me columns ka order compatible hona chahiye.

---

# 🔄 13. Correlated Subquery

### 📌 Definition

**Correlated Subquery** wo subquery hoti hai jo outer query ki current row ke data par depend karti hai.

### 🧠 Simple Hinglish

Normal subquery independently run ho sakti hai.

Lekin correlated subquery **Outer Query se value leti hai**.

```text
Outer Query
     ↓
Current Row
     ↓
Correlated Subquery
     ↓
Result
```

### Example

```sql
SELECT S1.Name, S1.Marks
FROM Student AS S1
WHERE S1.Marks > (
    SELECT AVG(S2.Marks)
    FROM Student AS S2
    WHERE S2.City = S1.City
);
```

### 🧠 Explanation

Yahan subquery:

```sql
S2.City = S1.City
```

outer query ki current row ke `City` par depend kar rahi hai.

Isliye ye **Correlated Subquery** hai.

> 💡 Correlated subquery ko samajhne ke liye **Outer Query → Inner Query dependency** yaad rakho.

---

# 🪆 14. Nested Subquery

### 📌 Definition

Jab ek subquery ke andar bhi ek aur subquery ho, to use **Nested Subquery** kaha ja sakta hai.

### Structure

```text
Main Query
    ↓
Subquery
    ↓
Nested Subquery
```

### Example Structure

```sql
SELECT Name
FROM Student
WHERE Marks > (
    SELECT AVG(Marks)
    FROM Student
    WHERE City IN (
        SELECT City
        FROM Student
        WHERE Name = 'Ravi'
    )
);
```

Yahan ek query ke andar another query aur uske andar bhi query hai.

---

# ⚖️ 15. Subquery with Comparison Operators

Single-value subquery ke saath comparison operators use kiye ja sakte hain.

### Common Operators

| Operator | Meaning |
|---|---|
| `=` | Equal |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `<=` | Less than or equal |
| `<>` | Not equal |

### Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks > (
    SELECT AVG(Marks)
    FROM Student
);
```

Yahan pehle average marks calculate honge aur phir usse greater students select honge.

---

# 📍 16. Subquery with WHERE

Subquery ka sabse common use `WHERE` clause ke saath hota hai.

### Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks = (
    SELECT MAX(Marks)
    FROM Student
);
```

### 🧠 Working

```text
Subquery
   ↓
MAX(Marks)
   ↓
Highest Marks
   ↓
Main Query
   ↓
Student with highest marks
```

---

# 📊 17. Subquery with FROM

Subquery ko `FROM` clause me bhi use kiya ja sakta hai.

Is case me subquery ka result ek **temporary result set** ki tarah use hota hai.

### Example

```sql
SELECT Name, Marks
FROM (
    SELECT Name, Marks
    FROM Student
    WHERE Marks >= 80
) AS TopStudents;
```

Yahan inner query pehle 80 ya usse zyada marks wale students ka result banati hai.

Phir outer query us result se data select karti hai.

> 💡 `FROM` me subquery ko generally **Derived Table** kaha jaata hai.

---

# 🧮 18. Subquery with Aggregate Function

Subquery ke andar aggregate functions bhi use kiye ja sakte hain.

### Example

**Average marks se zyada marks wale students:**

```sql
SELECT Name, Marks
FROM Student
WHERE Marks > (
    SELECT AVG(Marks)
    FROM Student
);
```

### Working

```text
AVG(Marks)
    ↓
Average Marks
    ↓
Marks > Average
    ↓
Students
```

---

# 🔍 19. Subquery vs Normal Query

| Feature | Normal Query | Subquery |
|---|---|---|
| Query inside another query | No | Yes |
| Complexity | Usually simple | Complex problems solve kar sakti hai |
| Result | Directly use hota hai | Outer query me use hota hai |
| Parentheses | Not required for normal query | Generally used |

---

# 🔄 20. Subquery vs JOIN

| Feature | Subquery | JOIN |
|---|---|---|
| Purpose | Query ke result ko another query me use karna | Tables ke related rows combine karna |
| Structure | Query inside query | Tables ko join karna |
| Readability | Simple cases me easy | Multiple-table data ke liye useful |
| Performance | Query par depend karta hai | Query par depend karta hai |

> 💡 Dono ka purpose aur use-case alag ho sakta hai. Har situation me ek ko automatically better nahi maana jaata.

---

# 📌 21. Important Rules of Subqueries

- Subquery generally **parentheses `( )`** ke andar likhi jaati hai.
- Subquery ko outer query ke andar use kiya jaata hai.
- Single-row result ke liye comparison operators useful hain.
- Multiple-row result ke liye `IN`, `ANY`, `ALL` useful ho sakte hain.
- Correlated subquery outer query ki current row par depend karti hai.
- `FROM` ke andar subquery use karne par alias dena important hota hai.
- Multiple-column comparison me columns compatible hone chahiye.

---

# ⚠️ 22. Common Mistakes

### ❌ Mistake 1: Multiple values ke saath `=` use karna

Agar subquery multiple values return karti hai:

```sql
WHERE Marks = (
    SELECT Marks
    FROM Student
);
```

to error aa sakta hai because `=` generally single value expect karta hai.

### ✅ Better Approach

Multiple values ke liye:

```sql
WHERE Marks IN (
    SELECT Marks
    FROM Student
);
```

---

### ❌ Mistake 2: FROM Sub
