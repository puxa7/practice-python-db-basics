**Schema (PostgreSQL v19 (Beta))**

    CREATE TABLE categories (
        id SERIAL PRIMARY KEY,
        name TEXT NOT NULL
    );
    
    CREATE TABLE articles (
        id SERIAL PRIMARY KEY,
        title TEXT NOT NULL,
        category_id INT REFERENCES categories(id)
    );

---

**Query #1**

    INSERT INTO categories (name) VALUES 
    	('Polityka'),
        ('Inwestowanie'),
        ('Zdrowie'),
        ('Sport');

There are no results to be displayed.

---
**Query #2**

    INSERT INTO articles (title, category_id) VALUES 
    	('Rekord w bieganiu!', 4),
        ('Kubica na podium!', 4),
        ('Jesienne przepisy', DEFAULT),
        ('S&P 500 nurkuje!', 2),
        ('Sposoby na lepszy sen', 3),
        ('Braun odpalił gaśnicę!', 1),
        ('Najsmaczniejsze ciasta!', DEFAULT);

There are no results to be displayed.

---
**Query #3**

    SELECT articles.title, categories.name 
    FROM categories 
    INNER JOIN articles 
    ON categories.id = articles.category_id;

| title                  | name         |
| ---------------------- | ------------ |
| Rekord w bieganiu!     | Sport        |
| Kubica na podium!      | Sport        |
| S&P 500 nurkuje!       | Inwestowanie |
| Sposoby na lepszy sen  | Zdrowie      |
| Braun odpalił gaśnicę! | Polityka     |

---
**Query #4**

    SELECT articles.title, categories.name 
    FROM articles 
    LEFT JOIN categories
    ON categories.id = articles.category_id;

| title                   | name         |
| ----------------------- | ------------ |
| Rekord w bieganiu!      | Sport        |
| Kubica na podium!       | Sport        |
| S&P 500 nurkuje!        | Inwestowanie |
| Sposoby na lepszy sen   | Zdrowie      |
| Braun odpalił gaśnicę!  | Polityka     |
| Jesienne przepisy       |              |
| Najsmaczniejsze ciasta! |              |

---

[View on DB Fiddle](https://www.db-fiddle.com/)