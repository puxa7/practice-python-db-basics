**Schema (PostgreSQL v19 (Beta))**

    CREATE TABLE students (
        id SERIAL PRIMARY KEY,
        full_name TEXT NOT NULL,
        birth_date DATE NOT NULL,
        email TEXT NOT NULL UNIQUE
    );

---

**Query #1**

    INSERT INTO students (full_name, birth_date, email) VALUES
    
        ('Liam Smith',        '2007-11-15', 'liam.smith@example.com'),
        ('Olivia Johnson',    '2008-01-22', 'olivia.johnson@example.com'),
        ('Noah Williams',     '2008-03-05', 'noah.williams@example.com'),
        ('Emma Brown',        '2008-06-18', 'emma.brown@example.com'),
        ('Oliver Jones',      '2008-09-30', 'oliver.jones@example.com'),
    
        ('Lucas Davis',       '2008-10-10', 'lucas.davis@example.com'),
    
        ('Sophia Miller',     '2008-10-11', 'sophia.miller@example.com'),
        ('Ethan Wilson',      '2008-12-01', 'ethan.wilson@example.com'),
        ('Ava Taylor',        '2009-02-14', 'ava.taylor@example.com'),
        ('Mason Anderson',    '2009-05-20', 'mason.anderson@example.com'),
        ('Isabella Thomas',   '2009-08-09', 'isabella.thomas@example.com');

There are no results to be displayed.

---
**Query #2**

    SELECT * FROM students WHERE birth_date <= (CURRENT_DATE - INTERVAL '18 years');

| id  | full_name      | birth_date | email                      |
| --- | -------------- | ---------- | -------------------------- |
| 1   | Liam Smith     | 2007-11-15 | liam.smith@example.com     |
| 2   | Olivia Johnson | 2008-01-22 | olivia.johnson@example.com |
| 3   | Noah Williams  | 2008-03-05 | noah.williams@example.com  |
| 4   | Emma Brown     | 2008-06-18 | emma.brown@example.com     |
| 5   | Oliver Jones   | 2008-09-30 | oliver.jones@example.com   |
| 6   | Lucas Davis    | 2008-10-10 | lucas.davis@example.com    |

---

[View on DB Fiddle](https://www.db-fiddle.com/)