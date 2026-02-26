# SQL Basics with JOIN Queries (Real-Time Examples)

## 1. What is SQL?

SQL (Structured Query Language) is used to communicate with databases.

------------------------------------------------------------------------

# Part 1: Basic SQL Queries

## Sample Table: students

  id   name    age   city
  ---- ------- ----- ---------
  1    Ravi    20    Chennai
  2    Meena   22    Madurai
  3    Arjun   21    Salem

------------------------------------------------------------------------

## SELECT

``` sql
SELECT * FROM students;
```

## WHERE

``` sql
SELECT * FROM students
WHERE age > 20;
```

## INSERT

``` sql
INSERT INTO students (id, name, age, city)
VALUES (4, 'Kumar', 23, 'Coimbatore');
```

## UPDATE

``` sql
UPDATE students
SET city = 'Trichy'
WHERE id = 1;
```

## DELETE

``` sql
DELETE FROM students
WHERE id = 3;
```

## ORDER BY

``` sql
SELECT * FROM students
ORDER BY age DESC;
```

------------------------------------------------------------------------

# Part 2: JOIN Queries (Real-Time Examples)

## Real-Time Scenario: College Management System

### Table 1: students

  student_id   name
  ------------ -------
  1            Ravi
  2            Meena
  3            Arjun

### Table 2: marks

  student_id   subject   marks
  ------------ --------- -------
  1            Maths     90
  2            Science   85
  4            English   70

------------------------------------------------------------------------

## 1. INNER JOIN

Returns matching records from both tables.

``` sql
SELECT students.name, marks.subject, marks.marks
FROM students
INNER JOIN marks
ON students.student_id = marks.student_id;
```

Result: - Ravi → Maths → 90 - Meena → Science → 85

------------------------------------------------------------------------

## 2. LEFT JOIN

Returns all records from left table + matching from right table.

``` sql
SELECT students.name, marks.subject, marks.marks
FROM students
LEFT JOIN marks
ON students.student_id = marks.student_id;
```

Result: - Ravi → Maths → 90 - Meena → Science → 85 - Arjun → NULL → NULL

------------------------------------------------------------------------

## 3. RIGHT JOIN

Returns all records from right table + matching from left table.

``` sql
SELECT students.name, marks.subject, marks.marks
FROM students
RIGHT JOIN marks
ON students.student_id = marks.student_id;
```

Result: - Ravi → Maths → 90 - Meena → Science → 85 - NULL → English → 70

------------------------------------------------------------------------

## 4. FULL JOIN

Returns all records from both tables.

``` sql
SELECT students.name, marks.subject, marks.marks
FROM students
FULL JOIN marks
ON students.student_id = marks.student_id;
```

------------------------------------------------------------------------

# Summary

  JOIN Type    What It Returns
  ------------ ------------------------------
  INNER JOIN   Matching records only
  LEFT JOIN    All left + matching right
  RIGHT JOIN   All right + matching left
  FULL JOIN    All records from both tables

------------------------------------------------------------------------

These JOIN queries are very important in real-time projects and
interviews.
