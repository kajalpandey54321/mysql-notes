# 🧮 **10 — SQL FUNCTIONS**

> 💡 **SQL Functions** predefined operations hote hain jo data par calculation, conversion, formatting ya information obtain karne ke kaam aate hain.

---

# 📌 1. What is SQL Function?

### 📝 Definition

A **SQL Function** is a predefined operation that performs a specific task on data and returns a result.

### 💡 Hinglish Explanation

SQL function ko ek **ready-made formula/tool** ki tarah samajh sakte hain.

Humein har calculation manually karne ki zarurat nahi hoti. SQL mein already bahut saare functions available hote hain.

### 🎯 Example

Agar humein students ke marks ka total chahiye:

```sql
SELECT SUM(Marks)
FROM Student;
```

Yahaan `SUM()` function marks ka total calculate karta hai.

---

# 📚 2. Types of SQL Functions

SQL functions ko mainly do categories mein samjha ja sakta hai:

| 🔢 Type | 📝 Meaning |
|---|---|
| **Single-Row Functions** | Har row par separately work karte hain |
| **Aggregate Functions** | Multiple rows ke data par work karke generally ek result dete hain |

---

# 1️⃣ 🔹 SINGLE-ROW FUNCTIONS

## 📌 Meaning

Single-row function ek time par **individual row/value** par operation perform karta hai aur har input ke liye result return karta hai.

Common examples:

- String Functions
- Numeric Functions
- Date/Time Functions

---

# 🔤 3. String Functions

String functions ka use **text/string data** ke saath operations karne ke liye hota hai.

---

## 🔹 UPPER()

`UPPER()` text ko uppercase mein convert karta hai.

### Example

```sql
SELECT UPPER(Name)
FROM Student;
```

### Example

```text
kajal → KAJAL
```

---

## 🔹 LOWER()

`LOWER()` text ko lowercase mein convert karta hai.

```sql
SELECT LOWER(Name)
FROM Student;
```

### Example

```text
KAJAL → kajal
```

---

## 🔹 LENGTH()

`LENGTH()` string ki length **bytes mein** return karta hai.

```sql
SELECT LENGTH(Name)
FROM Student;
```

Example:

```text
Kajal → 5
```

> 💡 MySQL mein multibyte characters ke case mein `LENGTH()` bytes count karta hai, jabki character count ke liye `CHAR_LENGTH()` use kiya ja sakta hai.

---

## 🔹 CONCAT()

`CONCAT()` ka use multiple strings ko **combine** karne ke liye hota hai.

```sql
SELECT CONCAT(Name, ' - ', Course)
FROM Student;
```

Example output:

```text
Kajal - CSE
```

---

## 🔹 SUBSTRING()

`SUBSTRING()` string ke kisi specific part ko extract karta hai.

```sql
SELECT SUBSTRING(Name, 1, 3)
FROM Student;
```

Agar Name `Kajal` hai, to result:

```text
Kaj
```

---

## 📊 String Functions Summary

| Function | Purpose |
|---|---|
| `UPPER()` | Uppercase |
| `LOWER()` | Lowercase |
| `LENGTH()` | String ki length in bytes |
| `CHAR_LENGTH()` | Characters ki count |
| `CONCAT()` | Strings combine |
| `SUBSTRING()` | String ka part extract |

---

# 🔢 4. Numeric Functions

Numeric functions ka use numbers par **calculation ya mathematical operation** perform karne ke liye hota hai.

---

## 🔹 ROUND()

`ROUND()` number ko specified decimal places tak round karta hai.

```sql
SELECT ROUND(85.678, 2);
```

Result:

```text
85.68
```

---

## 🔹 CEIL()

`CEIL()` value ko next greater integer ki taraf round karta hai.

```sql
SELECT CEIL(85.2);
```

Result:

```text
86
```

---

## 🔹 FLOOR()

`FLOOR()` value ko lower integer ki taraf round karta hai.

```sql
SELECT FLOOR(85.9);
```

Result:

```text
85
```

---

## 🔹 ABS()

`ABS()` number ki absolute value return karta hai.

```sql
SELECT ABS(-25);
```

Result:

```text
25
```

---

## 📊 Numeric Functions Summary

| Function | Purpose |
|---|---|
| `ROUND()` | Number round karna |
| `CEIL()` | Upper integer |
| `FLOOR()` | Lower integer |
| `ABS()` | Absolute value |

---

# 📅 5. Date and Time Functions

Date/Time functions ka use date aur time ke saath kaam karne ke liye hota hai.

---

## 🔹 CURDATE()

Current date return karta hai.

```sql
SELECT CURDATE();
```

Example result:

```text
2026-09-06
```

---

## 🔹 CURTIME()

Current time return karta hai.

```sql
SELECT CURTIME();
```

---

## 🔹 NOW()

Current date aur time return karta hai.

```sql
SELECT NOW();
```

Example:

```text
2026-09-06 21:30:15
```

---

## 📊 Date/Time Functions Summary

| Function | Purpose |
|---|---|
| `CURDATE()` | Current date |
| `CURTIME()` | Current time |
| `NOW()` | Current date + time |

---

# 2️⃣ 🔹 AGGREGATE FUNCTIONS

## 📌 Meaning

Aggregate functions multiple rows ke data par calculation perform karke generally **ek summarized result** return karte hain.

Common aggregate functions:

- `COUNT()`
- `SUM()`
- `AVG()`
- `MAX()`
- `MIN()`

---

# 🔢 6. COUNT()

`COUNT()` records/values ki counting ke liye use hota hai.

### 🔹 All Rows Count

```sql
SELECT COUNT(*)
FROM Student;
```

Ye table ki total rows count karega.

### 🔹 Specific Column Count

```sql
SELECT COUNT(Email)
FROM Student;
```

Ye `Email` column ki non-NULL values count karega.

> 💡 `COUNT(*)` aur `COUNT(column)` ka result same zaroori nahi hai.

---

# ➕ 7. SUM()

`SUM()` numeric values ka **total** calculate karta hai.

```sql
SELECT SUM(Marks)
FROM Student;
```

Example:

```text
Marks:
80
75
90

SUM = 245
```

---

# 📊 8. AVG()

`AVG()` numeric values ka **average** calculate karta hai.

```sql
SELECT AVG(Marks)
FROM Student;
```

Example:

```text
80 + 75 + 90 = 245

Average = 245 / 3
```

---

# 🔝 9. MAX()

`MAX()` column ki **highest value** return karta hai.

```sql
SELECT MAX(Marks)
FROM Student;
```

Example:

```text
80
75
90

MAX = 90
```

---

# 🔽 10. MIN()

`MIN()` column ki **lowest value** return karta hai.

```sql
SELECT MIN(Marks)
FROM Student;
```

Example:

```text
80
75
90

MIN = 75
```

---

# 📊 Aggregate Functions Summary

| Function | Purpose |
|---|---|
| `COUNT()` | Count |
| `SUM()` | Total |
| `AVG()` | Average |
| `MAX()` | Highest value |
| `MIN()` | Lowest value |

### 🧠 Easy Trick

```text
COUNT → Kitne?
SUM   → Total kitna?
AVG   → Average kitna?
MAX   → Sabse bada?
MIN   → Sabse chhota?
```

---

# 🏫 🎯 Real-Life Student Example

Suppose `Student` table mein:

| ID | Name | Marks |
|---:|---|---:|
| 101 | Kajal | 85 |
| 102 | Rahul | 72 |
| 103 | Aman | 91 |
| 104 | Priya | 65 |

### 🔹 Total Students

```sql
SELECT COUNT(*)
FROM Student;
```

### 🔹 Total Marks

```sql
SELECT SUM(Marks)
FROM Student;
```

### 🔹 Average Marks

```sql
SELECT AVG(Marks)
FROM Student;
```

### 🔹 Highest Marks

```sql
SELECT MAX(Marks)
FROM Student;
```

### 🔹 Lowest Marks

```sql
SELECT MIN(Marks)
FROM Student;
```

---

# 🔗 11. Function with WHERE

Functions ko filtering ke saath bhi use kiya ja sakta hai.

### Example

CSE students ke highest marks:

```sql
SELECT MAX(Marks)
FROM Student
WHERE Course = 'CSE';
```

Yahaan:

1. `WHERE` CSE students ko select karta hai.
2. `MAX()` unmein highest marks find karta hai.

---

# 📋 12. Function with Column Alias

Function ke result ko readable name dene ke liye **alias** use kar sakte hain.

```sql
SELECT AVG(Marks) AS Average_Marks
FROM Student;
```

Result ka column name:

```text
Average_Marks
```

ho sakta hai.

---

# 📊 13. Single-Row vs Aggregate Functions

| Feature | Single-Row Function | Aggregate Function |
|---|---|---|
| Works on | Individual value/row | Multiple rows |
| Result | Generally each input row ke liye | Generally summarized result |
| Examples | `UPPER()`, `ROUND()` | `SUM()`, `AVG()` |
| Main use | Data transformation | Data analysis/summary |

---

# 🧩 14. Important Function Examples

### 🔹 Name Uppercase

```sql
SELECT UPPER(Name)
FROM Student;
```

### 🔹 Name + Course

```sql
SELECT CONCAT(Name, ' - ', Course) AS Student_Info
FROM Student;
```

### 🔹 Total Students

```sql
SELECT COUNT(*) AS Total_Students
FROM Student;
```

### 🔹 Average Marks

```sql
SELECT AVG(Marks) AS Average_Marks
FROM Student;
```

### 🔹 Highest Marks

```sql
SELECT MAX(Marks) AS Highest_Marks
FROM Student;
```

---

# ⚠️ Important Points

1. SQL functions predefined operations perform karte hain.
2. Functions data ko calculate, transform ya summarize karne mein help karte hain.
3. Single-row functions individual values/rows par work karte hain.
4. Aggregate functions multiple rows ko summarize karte hain.
5. `COUNT(*)` total rows count karta hai.
6. `SUM()` numeric values ka total deta hai.
7. `AVG()` average calculate karta hai.
8. `MAX()` highest value deta hai.
9. `MIN()` lowest value deta hai.
10. String functions text data ke saath kaam karte hain.
11. Numeric functions numbers par operation perform karte hain.
12. Date/Time functions date aur time ke saath kaam karte hain.
13. Function result ko readable banane ke liye `AS` alias use kar sakte hain.

---

# 📝 🎓 Exam Point of View

### Q1. What is an SQL Function?

**Answer:**  
An SQL function is a predefined operation that performs a specific task on data and returns a result.

---

### Q2. What are the main types of SQL Functions?

**Answer:**

The main types are:

1. **Single-Row Functions**
2. **Aggregate Functions**

---

### Q3. What are Aggregate Functions?

**Answer:**  
Aggregate functions perform calculations on multiple rows and generally return a single summarized result.

Examples:

```text
COUNT()
SUM()
AVG()
MAX()
MIN()
```

---

### Q4. What is the use of COUNT()?

**Answer:**  
`COUNT()` is used to count rows or non-NULL values in a column.

Example:

```sql
SELECT COUNT(*)
FROM Student;
```

---

### Q5. What is the use of SUM()?

**Answer:**  
`SUM()` is used to calculate the total of numeric values.

```sql
SELECT SUM(Marks)
FROM Student;
```

---

### Q6. What is the use of AVG()?

**Answer:**  
`AVG()` is used to calculate the average of numeric values.

```sql
SELECT AVG(Marks)
FROM Student;
```

---

### Q7. What is the difference between MAX() and MIN()?

**Answer:**

| MAX() | MIN() |
|---|---|
| Highest value return karta hai | Lowest value return karta hai |
| Example: highest marks | Example: lowest marks |

---

### Q8. Write any five aggregate functions.

**Answer:**

1. `COUNT()`
2. `SUM()`
3. `AVG()`
4. `MAX()`
5. `MIN()`

---

# 🧠 ⭐ Quick Revision

```text
SQL FUNCTIONS
│
├── Single-Row Functions
│   ├── String
│   │   ├── UPPER()
│   │   ├── LOWER()
│   │   ├── LENGTH()
│   │   ├── CONCAT()
│   │   └── SUBSTRING()
│   │
│   ├── Numeric
│   │   ├── ROUND()
│   │   ├── CEIL()
│   │   ├── FLOOR()
│   │   └── ABS()
│   │
│   └── Date/Time
│       ├── CURDATE()
│       ├── CURTIME()
│       └── NOW()
│
└── Aggregate Functions
    ├── COUNT() → Count
    ├── SUM()   → Total
    ├── AVG()   → Average
    ├── MAX()   → Highest
    └── MIN()   → Lowest
```

> 💡 **One-Line Revision:**  
> **Single-Row Functions → Individual data par kaam**  
> **Aggregate Functions → Multiple rows ka summary**
