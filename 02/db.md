**Schema (PostgreSQL v19 (Beta))**

    CREATE TABLE posts (
    	id SERIAL PRIMARY KEY,
        title TEXT NOT NULL,
      	content TEXT,
      	created_at TIMESTAMP DEFAULT NOW()
    );

---

**Query #1**

    INSERT INTO posts (title, content, created_at) VALUES 
    	('post 1', 'Lorem ipsum', NOW() - INTERVAL '14 day'), 
        ('post 2', 'Lorem ipsum', NOW() - INTERVAL '13 day'),
        ('post 3', 'Lorem ipsum', NOW() - INTERVAL '12 day'),
        ('post 4', 'Lorem ipsum', NOW() - INTERVAL '11 day'),
        ('post 5', 'Lorem ipsum', NOW() - INTERVAL '10 day'),
        ('post 6', 'Lorem ipsum', NOW() - INTERVAL '9 day'),
        ('post 7', 'Lorem ipsum', NOW() - INTERVAL '8 day'),
        ('post 8', 'Lorem ipsum', NOW() - INTERVAL '7 day'),
        ('post 9', 'Lorem ipsum', NOW() - INTERVAL '6 day'),
        ('post 10', 'Lorem ipsum', NOW() - INTERVAL '5 day'),
        ('post 11', 'Lorem ipsum', NOW() - INTERVAL '4 day'),
        ('post 12', 'Lorem ipsum', NOW() - INTERVAL '3 day'),
        ('post 13', 'Lorem ipsum', NOW() - INTERVAL '2 day'),
        ('post 14', 'Lorem ipsum', NOW() - INTERVAL '1 day'),
        ('post 15', 'Lorem ipsum', DEFAULT);

There are no results to be displayed.

---
**Query #2**

    SELECT * FROM posts ORDER BY created_at DESC LIMIT 5;

| id  | title   | content     | created_at                 |
| --- | ------- | ----------- | -------------------------- |
| 15  | post 15 | Lorem ipsum | 2026-10-10 13:32:57.622499 |
| 14  | post 14 | Lorem ipsum | 2026-10-09 13:32:57.622499 |
| 13  | post 13 | Lorem ipsum | 2026-10-08 13:32:57.622499 |
| 12  | post 12 | Lorem ipsum | 2026-10-07 13:32:57.622499 |
| 11  | post 11 | Lorem ipsum | 2026-10-06 13:32:57.622499 |

---
**Query #3**

    SELECT * FROM posts ORDER BY created_at DESC LIMIT 5 OFFSET 5;

| id  | title   | content     | created_at                 |
| --- | ------- | ----------- | -------------------------- |
| 10  | post 10 | Lorem ipsum | 2026-10-05 13:32:57.622499 |
| 9   | post 9  | Lorem ipsum | 2026-10-04 13:32:57.622499 |
| 8   | post 8  | Lorem ipsum | 2026-10-03 13:32:57.622499 |
| 7   | post 7  | Lorem ipsum | 2026-10-02 13:32:57.622499 |
| 6   | post 6  | Lorem ipsum | 2026-10-01 13:32:57.622499 |

---

[View on DB Fiddle](https://www.db-fiddle.com/)