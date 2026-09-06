# 🧩 **06 — DATA TYPES IN MYSQL**

> 💡 **Data Type** batata hai ki kisi table ke column me **kis type ka data store** kiya jayega.

---

# 📌 1. Data Type Kya Hota Hai?

### 🔹 Definition

A **Data Type** specifies the type of data that can be stored in a column or variable.

### 🧠 Easy Hinglish

Jab hum MySQL me table create karte hain, to har column ke saath uska **Data Type** define karte hain.

For example:

```sql
CREATE TABLE Student (
    id INT,
    name VARCHAR(50),
    marks INT
);
```

Yaha:

- `id` → `INT`
- `name` → `VARCHAR(50)`
- `marks` → `INT`

Matlab `id` aur `marks` me integer values aur `name` me text store kiya jayega.

---

# 🎯 2. Data Types Ki Zarurat Kyu Hoti Hai?

Data Types important hain because:

1. 📦 Data ko properly store karte hain.
2. 💾 Storage ko manage karne me help karte hain.
3. 🔍 Data ko identify karna easy hota hai.
4. ✅ Invalid type ke data ko control karne me help karte hain.
5. ⚡ Database operations ko efficient banane me help karte hain.

---

# 🧩 3. MySQL Data Types Ke Main Categories

MySQL me commonly used data types ko broadly in categories me samjha ja sakta hai:

```text
MySQL Data Types
      │
      ├── 🔢 Numeric
      │
      ├── 🔤 String
      │
      ├── 📅 Date and Time
      │
      ├── 📦 JSON
      │
      └── 📍 Spatial
```

Beginner level par **Numeric, String aur Date/Time** data types sabse important hain.

---

# 🔢 4. Numeric Data Types

Numeric data types ka use **numbers** store karne ke liye hota hai.

Examples:

```text
10
25
100
85.5
-20
```

Common numeric data types:

| Data Type | Use |
|---|---|
| `INT` | Whole numbers |
| `BIGINT` | Very large whole numbers |
| `DECIMAL` | Exact decimal values |
| `FLOAT` | Approximate decimal values |
| `DOUBLE` | Larger approximate decimal values |

---

# 🔢 5. INT

## 📖 Definition

`INT` ka use **whole numbers / integer values** store karne ke liye hota hai.

### 💻 Examples

```text
10
25
100
500
-20
```

### 📝 Example

```sql
CREATE TABLE Student (
    id INT,
    marks INT
);
```

Yaha `id` aur `marks` me integer values store ki ja sakti hain.

### 💡 Real-Life Uses

- Student ID
- Roll Number
- Age
- Marks
- Quantity

---

# 🔢 6. BIGINT

## 📖 Definition

`BIGINT` ka use **bahut bade whole numbers** store karne ke liye kiya jata hai.

### 💻 Example

```sql
CREATE TABLE Account (
    account_number BIGINT
);
```

### 📌 Real-Life Use

Jab number ka size normal `INT` se bahut bada ho sakta hai, tab `BIGINT` useful hota hai.

> 💡 **Remember:** `BIGINT` = **Big Integer**

---

# 💰 7. DECIMAL

## 📖 Definition

`DECIMAL` ka use **exact decimal values** store karne ke liye kiya jata hai.

Ye financial aur calculation-related data ke liye commonly useful hota hai.

### 📝 Syntax

```sql
DECIMAL(M,D)
```

Yaha:

- `M` = total number of digits
- `D` = decimal point ke baad digits

### 💻 Example

```sql
price DECIMAL(10,2)
```

Example values:

```text
499.99
1250.50
9999.00
```

### 🛒 Real-Life Use

- Product Price
- Fees
- Salary amount
- Payment amount

> 💡 **Remember:** Money ke exact values ke liye `DECIMAL` commonly preferred hota hai.

---

# 🔢 8. FLOAT

## 📖 Definition

`FLOAT` ka use **approximate decimal values** store karne ke liye hota hai.

### 💻 Example

```sql
temperature FLOAT;
```

Example:

```text
36.5
98.6
25.75
``

### 📌 Use

- Scientific calculations
- Measurements
- Approximate numeric values

> ⚠️ `FLOAT` exact decimal representation ke liye suitable nahi hota in situations where exact precision is required.

---

# 🔢 9. DOUBLE

## 📖 Definition

`DOUBLE` bhi approximate decimal values store karta hai aur `FLOAT` se larger range/precision provide kar sakta hai.

### 💻 Example

```sql
distance DOUBLE;
```

Example:

```text
12345.6789
```

### 📌 Use

- Scientific calculations
- Engineering calculations
- Large approximate decimal values

---

# 🔤 10. String Data Types

String data types ka use **text/characters** store karne ke liye hota hai.

Examples:

```text
Kajal
Computer Science
Jaunpur
India
```

Common string types:

| Data Type | Use |
|---|---|
| `CHAR` | Fixed-length text |
| `VARCHAR` | Variable-length text |
| `TEXT` | Large text |

---

# 🔤 11. CHAR

## 📖 Definition

`CHAR` ka use **fixed-length string** store karne ke liye hota hai.

### 📝 Syntax

```sql
CHAR(n)
```

### 💻 Example

```sql
gender CHAR(1);
```

Possible values:

```text
M
F
```

Another example:

```sql
code CHAR(5);
```

### 📌 Use

Jab data ki length generally fixed ho.

Examples:

- Country code
- Short code
- Fixed-length identifiers

> 💡 **CHAR = Fixed Length**

---

# 🔤 12. VARCHAR

## 📖 Definition

`VARCHAR` ka use **variable-length text** store karne ke liye hota hai.

### 📝 Syntax

```sql
VARCHAR(n)
```

### 💻 Example

```sql
name VARCHAR(50);
```

Possible values:

```text
Kajal
Rahul
Priya
```

### 📌 Real-Life Uses

- Name
- City
- Email
- Address
- Course name

### 💡 Example

```sql
CREATE TABLE Student (
    name VARCHAR(50),
    city VARCHAR(50),
    course VARCHAR(100)
);
```

> 💡 **VARCHAR = Variable Length Character**

---

# 📄 13. TEXT

## 📖 Definition

`TEXT` ka use **large amount of text** store karne ke liye hota hai.

### 💻 Example

```sql
description TEXT;
```

### 📌 Real-Life Uses

- Article
- Blog content
- Product description
- Long comments
- Detailed information

### 💡 Example

```sql
CREATE TABLE Blog (
    title VARCHAR(100),
    content TEXT
);
```

---

# ⚖️ 14. CHAR vs VARCHAR

| Feature | `CHAR` | `VARCHAR` |
|---|---|---|
| Length | Fixed | Variable |
| Example | `CHAR(10)` | `VARCHAR(10)` |
| Suitable for | Fixed-length values | Variable-length text |
| Example Use | Fixed codes | Names, emails |

### 🧠 Easy Trick

> 🔒 **CHAR = Fixed**
>
> 🔄 **VARCHAR = Variable**

---

# 📅 15. Date and Time Data Types

Date and time information store karne ke liye MySQL me different data types available hain.

Common types:

| Data Type | Use |
|---|---|
| `DATE` | Date |
| `TIME` | Time |
| `DATETIME` | Date + Time |
| `TIMESTAMP` | Date + Time with timestamp-related behavior |
| `YEAR` | Year |

---

# 📅 16. DATE

## 📖 Definition

`DATE` ka use **date** store karne ke liye hota hai.

### 📌 Format

```text
YYYY-MM-DD
```

### 💻 Example

```text
2026-09-06
```

### 📝 Table Example

```sql
CREATE TABLE Student (
    name VARCHAR(50),
    birth_date DATE
);
```

Data insert:

```sql
INSERT INTO Student
VALUES ('Kajal', '2006-05-15');
```

---

# ⏰ 17. TIME

## 📖 Definition

`TIME` ka use **time** store karne ke liye hota hai.

### 📌 Format

```text
HH:MM:SS
```

### 💻 Example

```text
14:30:00
```

### 📝 Example

```sql
CREATE TABLE Schedule (
    class_time TIME
);
```

---

# 📅⏰ 18. DATETIME

## 📖 Definition

`DATETIME` ka use **date aur time dono** store karne ke liye hota hai.

### 📌 Format

```text
YYYY-MM-DD HH:MM:SS
```

### 💻 Example

```text
2026-09-06 14:30:00
```

### 📝 Example

```sql
CREATE TABLE Appointment (
    appointment_time DATETIME
);
```

---

# ⏱️ 19. TIMESTAMP

## 📖 Definition

`TIMESTAMP` date aur time information store karne ke liye use hota hai aur timestamp-related automatic behaviors ke liye commonly useful hai.

### 💻 Example

```sql
CREATE TABLE Login (
    login_time TIMESTAMP
);
```

### 📌 Common Use

- Login time
- Record creation time
- Record update time

Example:

```sql
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
```

---

# 📆 20. YEAR

## 📖 Definition

`YEAR` ka use **year value** store karne ke liye kiya jata hai.

### 💻 Example

```sql
passing_year YEAR
```

Example value:

```text
2026
```

---

# 📦 21. BOOLEAN / BOOL

MySQL me `BOOLEAN` / `BOOL` commonly `TINYINT(1)` ke equivalent ke roop me treat kiya jata hai.

Iska use **True/False type information** represent karne ke liye kiya ja sakta hai.

### 💻 Example

```sql
is_active BOOLEAN;
```

Example:

```text
TRUE
FALSE
```

> 💡 MySQL internally Boolean ko numeric representation ke through handle karta hai.

---

# 📦 22. JSON

## 📖 Definition

`JSON` data type ka use **JSON formatted data** store karne ke liye kiya jata hai.

### 💻 Example

```sql
CREATE TABLE UserProfile (
    id INT,
    details JSON
);
```

Data:

```sql
INSERT INTO UserProfile
VALUES (
    1,
    '{"city":"Jaunpur","course":"CSE"}'
);
```

> 💡 Beginner level par JSON ko simply **structured data format** ke roop me samjho.

---

# 🖼️ 23. BLOB

## 📖 Definition

`BLOB` ka full form **Binary Large Object** hai.

Iska use binary data store karne ke liye hota hai.

Examples:

- Binary files
- Some image/file data
- Other binary information

### 💻 Example

```sql
document BLOB;
```

> 💡 Practical applications me large files ko directly database me store karne ke bajay file/object storage use karna bhi common approach hai.

---

# 🧩 24. Commonly Used Data Types

Beginner level par sabse important data types:

```text
🔢 Numeric
   ├── INT
   ├── BIGINT
   ├── DECIMAL
   ├── FLOAT
   └── DOUBLE

🔤 String
   ├── CHAR
   ├── VARCHAR
   └── TEXT

📅 Date & Time
   ├── DATE
   ├── TIME
   ├── DATETIME
   ├── TIMESTAMP
   └── YEAR

📦 Other
   ├── BOOLEAN
   ├── JSON
   └── BLOB
```

---

# 🏗️ 25. Data Types in a Table

Ek Student table ka example:

```sql
CREATE TABLE Student (
    id INT,
    name VARCHAR(50),
    age INT,
    marks DECIMAL(5,2),
    birth_date DATE,
    admission_time DATETIME,
    is_active BOOLEAN
);
```

### 📌 Is table me:

| Column | Data Type | Example |
|---|---|---|
| `id` | `INT` | `101` |
| `name` | `VARCHAR(50)` | `Kajal` |
| `age` | `INT` | `20` |
| `marks` | `DECIMAL(5,2)` | `85.50` |
| `birth_date` | `DATE` | `2006-05-15` |
| `admission_time` | `DATETIME` | `2026-09-06 10:30:00` |
| `is_active` | `BOOLEAN` | `TRUE` |

---

# 🧪 26. Complete Practical Example

### Step 1 — Database Create

```sql
CREATE DATABASE College;
```

### Step 2 — Database Select

```sql
USE College;
```

### Step 3 — Table Create

```sql
CREATE TABLE Student (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    marks DECIMAL(5,2),
    birth_date DATE,
    is_active BOOLEAN
);
```

### Step 4 — Data Insert

```sql
INSERT INTO Student
VALUES
(101, 'Kajal', 20, 85.50, '2006-05-15', TRUE),
(102, 'Rahul', 21, 78.75, '2005-08-20', TRUE);
```

### Step 5 — Data Display

```sql
SELECT * FROM Student;
```

### 📌 Example Output

| ID | Name | Age | Marks | Birth Date | Active |
|---:|---|---:|---:|---|---|
| 101 | Kajal | 20 | 85.50 | 2006-05-15 | 1 |
| 102 | Rahul | 21 | 78.75 | 2005-08-20 | 1 |

---

# ⚖️ 27. INT vs DECIMAL vs FLOAT vs DOUBLE

| Data Type | Data | Main Use |
|---|---|---|
| `INT` | Whole number | Age, ID, marks |
| `DECIMAL` | Exact decimal | Price, money |
| `FLOAT` | Approximate decimal | Measurements |
| `DOUBLE` | Larger approximate decimal | Scientific calculations |

### 🧠 Easy Trick

> 🔢 **INT → Whole Number**
>
> 💰 **DECIMAL → Exact Decimal**
>
> 🔢 **FLOAT → Approximate Decimal**
>
> 🔬 **DOUBLE → Larger Approximate Decimal**

---

# ⚖️ 28. DATE vs DATETIME vs TIME

| Data Type | Stores | Example |
|---|---|---|
| `DATE` | Date | `2026-09-06` |
| `TIME` | Time | `14:30:00` |
| `DATETIME` | Date + Time | `2026-09-06 14:30:00` |
| `YEAR` | Year | `2026` |

---

# 🎯 29. Choosing the Correct Data Type

Data type select karte time data ki nature dekho.

### 👤 Name

```sql
name VARCHAR(50)
```

### 🎂 Age

```sql
age INT
```

### 💰 Price

```sql
price DECIMAL(10,2)
```

### 📅 Date of Birth

```sql
birth_date DATE
```

### ⏰ Class Time

```sql
class_time TIME
```

### 📅⏰ Appointment

```sql
appointment_time DATETIME
```

### 📝 Long Description

```sql
description TEXT
```

---

# 📌 30. Important Points

- Data Type column me store hone wale data ka **type define** karta hai.
- `INT` whole numbers ke liye use hota hai.
- `BIGINT` large integer values ke liye use hota hai.
- `DECIMAL` exact decimal values ke liye useful hai.
- `FLOAT` aur `DOUBLE` approximate decimal values ke liye use hote hain.
- `CHAR` fixed-length string ke liye use hota hai.
- `VARCHAR` variable-length string ke liye use hota hai.
- `TEXT` large text ke liye use hota hai.
- `DATE` date store karta hai.
- `TIME` time store karta hai.
- `DATETIME` date + time store karta hai.
- `TIMESTAMP` date/time information ke liye commonly used hai.
- `YEAR` year store karta hai.
- `BOOLEAN` True/False information represent karne ke liye use ho sakta hai.
- `JSON` JSON data store kar sakta hai.
- `BLOB` binary data ke liye use hota hai.

---

# 📝 31. Exam Point of View

## ⭐ 2 Marks Questions

### Q1. What is a Data Type?

**Answer:**  
A Data Type defines the type of data that can be stored in a column or variable.

---

### Q2. What is INT?

**Answer:**  
`INT` is a numeric data type used to store whole numbers.

---

### Q3. What is VARCHAR?

**Answer:**  
`VARCHAR` is a string data type used to store variable-length text.

---

### Q4. What is DECIMAL?

**Answer:**  
`DECIMAL` is used to store exact decimal values, commonly for financial or precise numeric data.

---

### Q5. What is DATE?

**Answer:**  
`DATE` is a data type used to store date values in the format `YYYY-MM-DD`.

---

## ⭐ 5 Marks Question

### Q. Explain different types of data types in MySQL.

### Answer:

MySQL provides different data types for storing different kinds of data. They include:

1. **Numeric Data Types**  
   Used to store numbers. Examples are `INT`, `BIGINT`, `DECIMAL`, `FLOAT` and `DOUBLE`.

2. **String Data Types**  
   Used to store text. Examples are `CHAR`, `VARCHAR` and `TEXT`.

3. **Date and Time Data Types**  
   Used to store date and time values. Examples are `DATE`, `TIME`, `DATETIME`, `TIMESTAMP` and `YEAR`.

4. **Other Data Types**  
   MySQL also supports types such as `JSON`, `BLOB` and Boolean representation.

Data types help in storing data properly and efficiently.

---

# ❓ 32. Important Exam Questions

### 🔹 Short Questions

1. What is a Data Type?
2. Why are data types used in MySQL?
3. What is `INT`?
4. What is `BIGINT`?
5. What is `DECIMAL`?
6. What is `FLOAT`?
7. What is `DOUBLE`?
8. What is `CHAR`?
9. What is `VARCHAR`?
10. What is `TEXT`?
11. What is `DATE`?
12. What is `TIME`?
13. What is `DATETIME`?
14. What is `TIMESTAMP`?
15. What is `JSON`?
16. What is `BLOB`?

### 🔹 Long Questions

1. Explain different data types in MySQL with examples.
2. Explain numeric data types in MySQL.
3. Explain string data types in MySQL.
4. Explain date and time data types.
5. Differentiate between `CHAR` and `VARCHAR`.
6. Differentiate between `INT`, `DECIMAL`, `FLOAT` and `DOUBLE`.
7. Differentiate between `DATE`, `TIME` and `DATETIME`.

---

# ⚡ 33. Quick Revision

| 🧩 Data Type | 🎯 Use |
|---|---|
| `INT` | 🔢 Whole numbers |
| `BIGINT` | 🔢 Large whole numbers |
| `DECIMAL` | 💰 Exact decimal |
| `FLOAT` | 🔢 Approximate decimal |
| `DOUBLE` | 🔬 Larger approximate decimal |
| `CHAR` | 🔒 Fixed-length text |
| `VARCHAR` | 🔄 Variable-length text |
| `TEXT` | 📄 Large text |
| `DATE` | 📅 Date |
| `TIME` | ⏰ Time |
| `DATETIME` | 📅⏰ Date + Time |
| `TIMESTAMP` | ⏱️ Timestamp/date-time data |
| `YEAR` | 📆 Year |
| `BOOLEAN` | ✅ True/False representation |
| `JSON` | 📦 JSON data |
| `BLOB` | 🗃️ Binary data |

---

# 🧠 Easy Trick to Remember

> 🔢 **Number → INT / DECIMAL**
>
> 🔤 **Text → VARCHAR / CHAR / TEXT**
>
> 📅 **Date → DATE**
>
> ⏰ **Time → TIME**
>
> 📅⏰ **Date + Time → DATETIME**
>
> 💰 **Exact Money → DECIMAL**
>
> 📦 **JSON Data → JSON**

---

# 🎯 One-Line Summary

> **Data Types define what kind of data can be stored in a MySQL table column.**

