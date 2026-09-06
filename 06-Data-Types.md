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
