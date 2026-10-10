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
    	('post 1', 'Lorem ipsum', DEFAULT), 
        ('post 2', 'Lorem ipsum', NOW() - INTERVAL '1 day'),
        ('post 3', 'Lorem ipsum', NOW() - INTERVAL '1 month 15 days'),
        ('post 4', 'Lorem ipsum', NOW() - INTERVAL '2 year');

There are no results to be displayed.

---
**Query #2**

    SELECT * FROM posts;

| id  | title  | content     | created_at                 |
| --- | ------ | ----------- | -------------------------- |
| 1   | post 1 | Lorem ipsum | 2026-10-10 13:12:58.549606 |
| 2   | post 2 | Lorem ipsum | 2026-10-09 13:12:58.549606 |
| 3   | post 3 | Lorem ipsum | 2026-08-26 13:12:58.549606 |
| 4   | post 4 | Lorem ipsum | 2024-10-10 13:12:58.549606 |

---

[View on DB Fiddle](https://www.db-fiddle.com/)