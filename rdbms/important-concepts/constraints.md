# SQL Constraints

SQL constraints are used to **specify rules** for the data in a table.

- **Control what kind of data goes in**
- **Prevent mistakes**
- **Protect relationships between tables**

| Constraint | Purpose |
| --- | ---|
| `PRIMARY KEY` | Uniquely identifies each row in a table. A combination of a `NOT NULL` and `UNIQUE`.|
| `FOREIGN KEY` | Creates a **relationship** between two tables. **Prevents actions** that would **destroy** links between tables.|
| `NOT NULL`| Column **must have a value** (can’t be empty)|
| `UNIQUE` | Ensures all values in a column are **different** |
| `CHECK` | Ensures that the values in a column satisfies a **specific condition** |
| `DEFAULT` | Provides a **default value** if no value is given|

---

## ✅ Examples

### 1. **PRIMARY KEY**

```sql
CREATE TABLE Students (
  StudentID INT PRIMARY KEY,
  Name VARCHAR(100)
);
```

### 2. **FOREIGN KEY**

```sql
CREATE TABLE Enrollments (
  EnrollmentID INT PRIMARY KEY,
  StudentID INT,
  FOREIGN KEY (StudentID) REFERENCES Students(StudentID)
);
```

### 3. **NOT NULL**

```sql
CREATE TABLE Courses (
  CourseID INT PRIMARY KEY,
  CourseName VARCHAR(100) NOT NULL
);
```

### 4. **UNIQUE**

```sql
CREATE TABLE Users (
  UserID INT PRIMARY KEY,
  Email VARCHAR(100) UNIQUE
);
```

### 5. **CHECK**

```sql
CREATE TABLE Employees (
  EmpID INT PRIMARY KEY,
  Age INT CHECK (Age >= 18)
);
```

### 6. **DEFAULT**

```sql
CREATE TABLE Orders (
  OrderID INT PRIMARY KEY,
  Status VARCHAR(20) DEFAULT 'Pending'
);
```

---

## 🚨 Important Notes:

* We can **combine constraints** in one column.
* Some constraints (like `PRIMARY KEY`, `FOREIGN KEY`) can also be added after table creation using `ALTER TABLE`.

---