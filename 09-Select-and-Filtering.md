# 🔎 **09 — SELECT AND FILTERING**

> 💡 **SELECT** ka use database table se data ko retrieve/display karne ke liye hota hai, aur **Filtering** ka use sirf required records ko condition ke according select karne ke liye hota hai.

---

## 📌 1. SELECT Statement

### 📝 Definition

`SELECT` statement ka use table se **data retrieve** karne ke liye kiya jata hai.

### 🔹 Basic Syntax

```sql
SELECT column_name
FROM table_name;
```

### 🔹 Example

```sql
SELECT Name
FROM Student;
```

Ye `Student` table se sirf `Name` column display karega.

---

## 📌 2. Multiple Columns Select Karna

Agar humein ek se zyada columns chahiye, to unke names comma `,` se likhte hain.

### 🔹 Example

```sql
SELECT Name, Course, City
FROM Student;
```

Ye `Name`, `Course` aur `City` columns display karega.

---

## 📌 3. All Columns Select Karna

Table ke saare columns ko display karne ke liye `*` use karte hain.

### 🔹 Syntax

```sql
SELECT *
FROM table_name;
```

### 🔹 Example

```sql
SELECT *
FROM Student;
```

> 💡 `*` ka meaning hai **all columns**.

---

# 🎯 FILTERING DATA

## 📌 4. WHERE Clause

### 📝 Meaning

`WHERE` clause ka use data ko **condition ke basis par filter** karne ke liye hota hai.

### 🔹 Syntax

```sql
SELECT column_name
FROM table_name
WHERE condition;
```

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Course = 'CSE';
```

Ye sirf un students ko show karega jinka course **CSE** hai.

---

# 🔢 5. Comparison Operators

Conditions banane ke liye comparison operators use kiye jaate hain.

| Operator | Meaning |
|---|---|
| `=` | Equal to |
| `!=` | Not equal to |
| `<>` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal to |
| `<=` | Less than or equal to |

---

## 🔹 Equal To `=`

```sql
SELECT *
FROM Student
WHERE City = 'Jaunpur';
```

Sirf Jaunpur city wale records milenge.

---

## 🔹 Not Equal `!=`

```sql
SELECT *
FROM Student
WHERE Course != 'CSE';
```

CSE ke alawa doosre courses ke records milenge.

---

## 🔹 Greater Than `>`

```sql
SELECT *
FROM Student
WHERE Marks > 80;
```

80 se zyada marks wale students milenge.

---

## 🔹 Less Than `<`

```sql
SELECT *
FROM Student
WHERE Marks < 50;
```

50 se kam marks wale students milenge.

---

## 🔹 Greater Than or Equal To `>=`

```sql
SELECT *
FROM Student
WHERE Marks >= 60;
```

60 ya usse zyada marks wale records milenge.

---

## 🔹 Less Than or Equal To `<=`

```sql
SELECT *
FROM Student
WHERE Marks <= 40;
```

40 ya usse kam marks wale records milenge.

---

# 🧠 6. AND Operator

`AND` ka use tab hota hai jab **multiple conditions ek saath true** honi chahiye.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Course = 'CSE'
AND Marks >= 60;
```

Yahaan:

- Course CSE hona chahiye
- Marks 60 ya usse zyada hone chahiye

Dono conditions satisfy karne wale records milenge.

---

# 🧠 7. OR Operator

`OR` ka use tab hota hai jab **multiple conditions mein se koi ek true** ho.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Course = 'CSE'
OR Course = 'IT';
```

CSE **ya** IT course ke students milenge.

---

# 🚫 8. NOT Operator

`NOT` condition ka opposite result obtain karne ke liye use hota hai.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE NOT Course = 'CSE';
```

Isse CSE ke alawa doosre courses ke records mil sakte hain.

---

# 🔢 9. BETWEEN Operator

`BETWEEN` ka use kisi value ko **given range ke andar** check karne ke liye hota hai.

### 🔹 Syntax

```sql
SELECT *
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Marks BETWEEN 60 AND 80;
```

Ye 60 se 80 ke range mein marks wale records select karega.

> 💡 `BETWEEN` normally **inclusive** hota hai, yani starting aur ending values bhi include hoti hain.

---

# 📋 10. IN Operator

`IN` ka use multiple possible values mein se kisi value ko match karne ke liye hota hai.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Course IN ('CSE', 'IT', 'ECE');
```

Ye CSE, IT ya ECE course wale records return karega.

### 🧠 Easy Way

```text
IN = In these values
```

---

# 🔤 11. LIKE Operator

`LIKE` ka use text pattern search karne ke liye hota hai.

Isme commonly:

- `%`
- `_`

wildcards use hote hain.

---

## 🔹 `%` Wildcard

`%` zero, one ya multiple characters ko represent kar sakta hai.

### Example — Name A se Start

```sql
SELECT *
FROM Student
WHERE Name LIKE 'A%';
```

A se start hone wale names milenge.

### Example — Name A par End

```sql
SELECT *
FROM Student
WHERE Name LIKE '%A';
```

A par end hone wale names milenge.

### Example — Name mein "an"

```sql
SELECT *
FROM Student
WHERE Name LIKE '%an%';
```

Jin names mein `an` pattern present hai, woh match ho sakte hain.

---

# 🔤 12. `_` Wildcard

`_` exactly **one character** ko represent karta hai.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Name LIKE 'A___';
```

Yahaan `A` ke baad exactly 3 characters ka pattern match kiya ja raha hai.

> 💡 `%` = Multiple/zero characters  
> 💡 `_` = Exactly one character

---

# ❓ 13. IS NULL

`NULL` ka matlab hota hai ki column mein **value available nahi hai**.

NULL check karne ke liye `=` use nahi karna chahiye.

### 🔹 NULL Records

```sql
SELECT *
FROM Student
WHERE Phone IS NULL;
```

Ye un records ko select karega jinke `Phone` ki value NULL hai.

---

# ❌ 14. IS NOT NULL

Jin records mein NULL value nahi hai unhe find karne ke liye:

```sql
SELECT *
FROM Student
WHERE Phone IS NOT NULL;
```

---

# 📊 15. ORDER BY

`ORDER BY` ka use retrieved records ko **sort** karne ke liye hota hai.

### 🔹 Ascending Order

```sql
SELECT *
FROM Student
ORDER BY Marks ASC;
```

`ASC` ka meaning **Ascending** hai.

### 🔹 Descending Order

```sql
SELECT *
FROM Student
ORDER BY Marks DESC;
```

`DESC` ka meaning **Descending** hai.

### 🧠 Easy Trick

```text
ASC  → Small to Large
DESC → Large to Small
```

---

# 🎯 16. WHERE + ORDER BY

Dono ko ek saath bhi use kar sakte hain.

### 🔹 Example

```sql
SELECT *
FROM Student
WHERE Course = 'CSE'
ORDER BY Marks DESC;
```

Pehle CSE students filter honge, phir unhe marks ke descending order mein show kiya jayega.

---

# 🔢 17. LIMIT

`LIMIT` ka use result mein **maximum number of rows** control karne ke liye hota hai.

### 🔹 Example

```sql
SELECT *
FROM Student
LIMIT 5;
```

Maximum 5 rows return hongi.

### 🔹 Top 3 Highest Marks

```sql
SELECT *
FROM Student
ORDER BY Marks DESC
LIMIT 3;
```

Pehle marks descending order mein sort honge, phir top 3 records return honge.

---

# 🔄 18. SELECT Query ka Basic Order

Common SELECT query ko generally is order mein likha jata hai:

```text
SELECT
   ↓
FROM
   ↓
WHERE
   ↓
ORDER BY
   ↓
LIMIT
```

### 🔹 Example

```sql
SELECT Name, Marks
FROM Student
WHERE Marks >= 60
ORDER BY Marks DESC
LIMIT 5;
```

### 🧠 Is Query ka Meaning

1. `Student` table se data lo.
2. Sirf 60 ya usse zyada marks wale records lo.
3. Marks ko descending order mein arrange karo.
4. Maximum 5 records show karo.

---

# 📊 19. Useful Filtering Examples

### 🔹 CSE Students

```sql
SELECT *
FROM Student
WHERE Course = 'CSE';
```

### 🔹 70+ Marks

```sql
SELECT *
FROM Student
WHERE Marks >= 70;
```

### 🔹 60–90 Marks

```sql
SELECT *
FROM Student
WHERE Marks BETWEEN 60 AND 90;
```

### 🔹 CSE or IT

```sql
SELECT *
FROM Student
WHERE Course IN ('CSE', 'IT');
```

### 🔹 Name Starting with R

```sql
SELECT *
FROM Student
WHERE Name LIKE 'R%';
```

### 🔹 Missing Phone Number

```sql
SELECT *
FROM Student
WHERE Phone IS NULL;
```

---

# 🏫 🎯 Real-Life Example

Suppose college ke Student Database mein ye information hai:

| ID | Name | Course | Marks | City |
|---:|---|---|---:|---|
| 101 | Kajal | CSE | 85 | Jaunpur |
| 102 | Rahul | IT | 72 | Varanasi |
| 103 | Aman | CSE | 91 | Lucknow |
| 104 | Priya | ECE | 65 | Jaunpur |

### 🎯 Question:
CSE students ko highest marks se lowest marks ke order mein show karna hai.

### ✅ Query:

```sql
SELECT *
FROM Student
WHERE Course = 'CSE'
ORDER BY Marks DESC;
```

---

# 📌 Important Difference

## WHERE vs ORDER BY vs LIMIT

| Clause | Purpose |
|---|---|
| `WHERE` | Data filter karta hai |
| `ORDER BY` | Data sort karta hai |
| `LIMIT` | Number of result rows limit karta hai |

### 🧠 Easy Trick

```text
WHERE     → Kaunse records?
ORDER BY  → Kis order mein?
LIMIT     → Kitne records?
```

---

# ⚠️ Important Points

1. `SELECT` data retrieve karne ke liye use hota hai.
2. `WHERE` filtering ke liye use hota hai.
3. `AND` mein multiple conditions satisfy honi chahiye.
4. `OR` mein conditions mein se koi ek satisfy ho sakti hai.
5. `BETWEEN` range ke liye use hota hai.
6. `IN` multiple possible values ke liye useful hai.
7. `LIKE` pattern matching ke liye use hota hai.
8. `%` multiple/zero characters ko represent karta hai.
9. `_` exactly one character ko represent karta hai.
10. NULL check karne ke liye `IS NULL` use hota hai.
11. `ORDER BY` sorting ke liye use hota hai.
12. `LIMIT` result rows ki maximum quantity control karta hai.

---

# 📝 🎓 Exam Point of View

### Q1. What is SELECT statement?

**Answer:**  
`SELECT` is an SQL statement used to retrieve data from one or more tables.

---

### Q2. What is WHERE clause?

**Answer:**  
`WHERE` clause is used to filter records according to a specified condition.

**Example:**

```sql
SELECT *
FROM Student
WHERE Marks >= 60;
```

---

### Q3. What is the use of ORDER BY?

**Answer:**  
`ORDER BY` is used to sort the result of a query in ascending or descending order.

---

### Q4. What is BETWEEN operator?

**Answer:**  
`BETWEEN` operator is used to select values within a specified range. The boundary values are generally included.

---

### Q5. What is IN operator?

**Answer:**  
`IN` operator is used to match a value against a list of specified values.

---

### Q6. What is LIKE operator?

**Answer:**  
`LIKE` operator is used for pattern matching in text data.

---

### Q7. What is the difference between `%` and `_`?

**Answer:**

| `%` | `_` |
|---|---|
| Zero or more characters | Exactly one character |
| Used for flexible patterns | Used for single-character matching |

---

### Q8. How do you check NULL values?

**Answer:**

```sql
SELECT *
FROM Student
WHERE Phone IS NULL;
```

---

### Q9. What is LIMIT?

**Answer:**  
`LIMIT` is used to restrict the maximum number of rows returned by a query.

---

# 🧠 ⭐ Quick Revision

```text
SELECT    → Data retrieve
WHERE     → Data filter
AND       → Both/all conditions
OR        → Any condition
NOT       → Opposite condition
BETWEEN   → Range
IN        → Multiple values
LIKE      → Pattern search
%         → Multiple/zero characters
_         → One character
IS NULL   → NULL values
ORDER BY  → Sorting
ASC       → Small → Large
DESC      → Large → Small
LIMIT     → Result rows limit
```

> 💡 **One-Line Revision:**  
> **SELECT data → WHERE filter → ORDER BY sort → LIMIT result**
