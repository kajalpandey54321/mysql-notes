# 🔑 **13 — KEYS IN MYSQL**

---

## 📌 1. What is a Key?

Database me **Key** ek column ya columns ka group hota hai jo table ke records ko **uniquely identify** karne aur tables ke beech **relationship establish** karne me help karta hai.

### 🧠 Simple Hinglish

Key ka main kaam:

- Record ko identify karna
- Duplicate records ko control karna
- Tables ke beech relationship banana
- Data ko properly organize karna

> 💡 **Easy Example:**  
> College me har student ka ek unique **Roll Number** hota hai. Roll Number se kisi particular student ko identify kiya ja sakta hai.

---

## 🔐 2. Types of Keys

Database me commonly ye keys padhi jaati hain:

1. **Super Key**
2. **Candidate Key**
3. **Primary Key**
4. **Alternate Key**
5. **Foreign Key**
6. **Composite Key**

---

## ⭐ 3. Super Key

### 📌 Definition

**Super Key** ek column ya columns ka aisa combination hai jo table ke har record ko **uniquely identify** kar sakta hai.

### 🧠 Simple Hinglish

Agar kisi column ya columns ke combination se har row ko uniquely identify kiya ja sakta hai, to wo **Super Key** ho sakta hai.

### 📋 Example

| Student_ID | Roll_No | Name | Email |
|---|---|---|---|
| 101 | 501 | Ravi | ravi@gmail.com |
| 102 | 502 | Aman | aman@gmail.com |
| 103 | 503 | Neha | neha@gmail.com |

Agar `Student_ID` unique hai, to:

- `Student_ID` → Super Key
- `Student_ID + Name` → Super Key
- `Student_ID + Email` → Super Key

> 💡 **Important:** Super Key me extra columns ho sakte hain.

---

## 🎯 4. Candidate Key

### 📌 Definition

**Candidate Key** ek **minimal Super Key** hoti hai jo table ke record ko uniquely identify karti hai.

### 🧠 Simple Hinglish

Candidate Key bhi record ko uniquely identify karti hai, lekin usme **unnecessary column nahi hota**.

### 📋 Example

Agar Student table me ye columns unique hain:

```text
Student_ID
Roll_No
Email
```

To teeno Candidate Keys ho sakti hain:

```text
Student_ID → Candidate Key
Roll_No    → Candidate Key
Email      → Candidate Key
```

Inme se kisi **ek Candidate Key ko Primary Key** choose kiya ja sakta hai.

> 💡 **Easy Trick:**  
> Candidate Keys = Primary Key banne ke **candidates**.

---

## ⭐ 5. Primary Key

### 📌 Definition

**Primary Key** table me har record ko uniquely identify karne ke liye selected key hoti hai.

### 🧠 Simple Hinglish

Agar multiple Candidate Keys available hain, to unme se **ek ko Primary Key** select kiya ja sakta hai.

### Example

```text
Candidate Keys:
Student_ID
Roll_No
Email

Selected Primary Key:
Student_ID
```

> 💡 Primary Key ki detailed constraints hum **07 — Constraints** chapter me already cover kar chuke hain.

---

## 🔄 6. Alternate Key

### 📌 Definition

Jo **Candidate Key Primary Key ke liye select nahi hoti**, use **Alternate Key** kaha jaata hai.

### 🧠 Simple Hinglish

Maan lo 3 Candidate Keys hain:

```text
Student_ID
Roll_No
Email
```

Aur:

```text
Student_ID → Primary Key
```

select kar li.

To:

```text
Roll_No
Email
```

**Alternate Keys** hongi.

### 📊 Example

| Key | Status |
|---|---|
| Student_ID | Primary Key |
| Roll_No | Alternate Key |
| Email | Alternate Key |

> 💡 **Remember:**  
> Candidate Key jo Primary Key nahi bani = **Alternate Key**

---

## 🔗 7. Foreign Key

### 📌 Definition

**Foreign Key** ek table ka column hota hai jo kisi doosre table ki key, usually **Primary Key**, ko reference karta hai.

### 🧠 Simple Hinglish

Foreign Key ka main purpose hai **do tables ke beech relationship establish karna**.

### Example

**Student Table**

| Student_ID | Name |
|---|---|
| 101 | Ravi |
| 102 | Aman |

**Course Table**

| Course_ID | Student_ID | Course |
|---|---|---|
| 1 | 101 | CSE |
| 2 | 102 | IT |

Yahan `Course.Student_ID` ek **Foreign Key** ho sakti hai.

> 💡 Foreign Key ka detailed explanation hum **07 — Constraints** aur **12 — Joins** chapters me cover kar chuke hain.

---

## 🧩 8. Composite Key

### 📌 Definition

Jab **two or more columns together** kisi record ko uniquely identify karte hain, to unka combination **Composite Key** kehlata hai.

### 🧠 Simple Hinglish

Kabhi-kabhi ek single column unique nahi hota. Aise case me multiple columns ko combine karke unique identification ki jaati hai.

### 📋 Example

**Student_Course Table**

| Student_ID | Course_ID | Marks |
|---|---|---|
| 101 | 1 | 85 |
| 101 | 2 | 90 |
| 102 | 1 | 78 |

Yahan:

```text
Student_ID + Course_ID
        ↓
   Composite Key
```

### 💻 MySQL Example

```sql
CREATE TABLE Student_Course (
    Student_ID INT,
    Course_ID INT,
    Marks INT,
    PRIMARY KEY (Student_ID, Course_ID)
);
```

Yahan `Student_ID + Course_ID` milkar **Composite Primary Key** banate hain.

---

## 📊 9. Super Key vs Candidate Key

| Feature | Super Key | Candidate Key |
|---|---|---|
| Unique identification | Yes | Yes |
| Extra columns | Ho sakte hain | Nahi |
| Minimal | Not necessary | Yes |
| Primary Key ban sakti hai | Possible | Yes |
| Example | Student_ID + Name | Student_ID |

### 🎯 Easy Way

```text
Super Key
    ↓
Unnecessary columns remove
    ↓
Candidate Key
```

---

## 🔑 10. Candidate Key vs Primary Key

| Feature | Candidate Key | Primary Key |
|---|---|---|
| Number | Multiple ho sakti hain | One selected key |
| Purpose | Primary Key ke candidates | Main identification key |
| Selection | Available candidates | Selected Candidate Key |
| Uniqueness | Yes | Yes |

### Example

```text
Candidate Keys:
Student_ID
Roll_No
Email

        ↓ Selection

Primary Key:
Student_ID
```

---

## 🔄 11. Primary Key vs Alternate Key

| Feature | Primary Key | Alternate Key |
|---|---|---|
| Selection | Selected Candidate Key | Remaining Candidate Key |
| Main key | Yes | No |
| Unique identification | Yes | Yes |
| Source | Candidate Key | Candidate Key |

### Example

```text
Candidate Keys:
Student_ID
Roll_No
Email

Primary Key:
Student_ID

Alternate Keys:
Roll_No
Email
```

---

## 🧩 12. Key Relationship

```text
                    KEYS
                      |
        ┌─────────────┴─────────────┐
        ↓                           ↓
  Identification              Relationship
        |                           |
   ┌────┴────┐                 Foreign Key
   ↓         ↓
Super     Candidate
 Key         |
             ↓
       ┌─────┴─────┐
       ↓           ↓
   Primary      Alternate
     Key           Key

Composite Key
      ↓
Multiple columns
used together
```

---

## 📚 13. Complete Comparison of Keys

| Key | Main Purpose |
|---|---|
| **Super Key** | Record ko uniquely identify karna |
| **Candidate Key** | Minimal unique identifier |
| **Primary Key** | Selected main unique identifier |
| **Alternate Key** | Candidate Key jo Primary Key nahi bani |
| **Foreign Key** | Tables ke beech relationship |
| **Composite Key** | Multiple columns together unique identification |

---

## 🧠 14. Easy Way to Remember

### 🔐 Super Key
**Unique identification + extra columns possible**

### 🎯 Candidate Key
**Minimal Super Key**

### ⭐ Primary Key
**Selected Candidate Key**

### 🔄 Alternate Key
**Candidate Key jo select nahi hui**

### 🔗 Foreign Key
**Tables ko connect karti hai**

### 🧩 Composite Key
**Multiple columns together**

---

## 📌 15. Important Points

- **Key** records ko identify aur organize karne me help karti hai.
- **Super Key** unique identification provide karti hai.
- **Candidate Key** minimal Super Key hoti hai.
- **Primary Key** Candidate Keys me se selected key hoti hai.
- **Alternate Key** non-selected Candidate Key hoti hai.
- **Foreign Key** tables ke beech relationship establish karti hai.
- **Composite Key** multiple columns ka combination hoti hai.
- Ek table me multiple Candidate Keys ho sakti hain.
- Candidate Keys me se ek ko Primary Key select kiya ja sakta hai.

---

## ✍️ 16. Exam Point of View

### ⭐ 2 Marks Questions

**Q1. What is a Key?**  
A key is a column or combination of columns used to uniquely identify records or establish relationships between tables.

**Q2. What is a Super Key?**  
A Super Key is a column or combination of columns that can uniquely identify each record in a table.

**Q3. What is a Candidate Key?**  
A Candidate Key is a minimal Super Key that uniquely identifies each record.

**Q4. What is an Alternate Key?**  
An Alternate Key is a Candidate Key that is not selected as the Primary Key.

**Q5. What is a Composite Key?**  
A Composite Key is a key formed by combining two or more columns.

---

## ⭐ 17. 5 Marks Question

### Q. Explain different types of keys in DBMS.

**Answer:**

Keys are used to uniquely identify records and establish relationships between tables. The major types of keys are:

1. **Super Key** – Uniquely identifies a record and may contain extra columns.
2. **Candidate Key** – A minimal Super Key.
3. **Primary Key** – Selected Candidate Key used as the main identifier.
4. **Alternate Key** – Candidate Key that is not selected as Primary Key.
5. **Foreign Key** – Used to establish a relationship between tables.
6. **Composite Key** – Formed using two or more columns.

---

## 📝 18. Important Exam Questions

### Short Questions

1. What is a Key?
2. Define Super Key.
3. What is a Candidate Key?
4. What is an Alternate Key?
5. What is a Composite Key?
6. What is a Foreign Key?
7. What is the difference between Super Key and Candidate Key?
8. What is the difference between Candidate Key and Primary Key?

### Long Questions

1. Explain different types of keys with examples.
2. Explain Super Key and Candidate Key.
3. Differentiate between Primary Key and Alternate Key.
4. Explain Composite Key with an example.
5. Explain the relationship between Candidate Key, Primary Key and Alternate Key.

---

# ⚡ 19. Quick Revision

| Key | Remember |
|---|---|
| 🔐 **Super Key** | Unique identification |
| 🎯 **Candidate Key** | Minimal Super Key |
| ⭐ **Primary Key** | Selected Candidate Key |
| 🔄 **Alternate Key** | Non-selected Candidate Key |
| 🔗 **Foreign Key** | Connects tables |
| 🧩 **Composite Key** | Multiple columns together |

---

# ✅ Final Summary

**Keys are an important part of database design.**

They help in:

- **Uniquely identifying records**
- **Maintaining data organization**
- **Establishing relationships between tables**

### 🔥 Most Important Flow

```text
Super Key
    ↓
Candidate Key
    ↓
┌───────────────┐
↓               ↓
Primary       Alternate
Key              Key
```

### 🔗 Remember

```text
Foreign Key → Tables ke beech relationship

Composite Key → 2 or more columns together
```

---
