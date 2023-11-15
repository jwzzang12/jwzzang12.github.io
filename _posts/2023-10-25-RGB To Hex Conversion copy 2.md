---
title: SQL Lesson Week 1 & Week 2
date: 2023-11-15 13:30:00 +0100
categories: [SQL, Database]
tags: [sql] # TAG names should always be lowercase
author: <author_id>
---

- Create a new Database called SHOP.
- Add a new table called SALES1.

```sql
CREATE DATABASE shop;
USE shop;

CREATE TABLE sales1(
Store VARCHAR(50) NOT NULL,
Week INT NOT NULL,
Day VARCHAR(10) NOT NULL,
SalesPerson VARCHAR(50) NOT NULL,
-- Wrong way
SalesAmount DECIMAL NOT NULL,
Month VARCHAR(3) NOT NULL
);

SELECT * FROM shop.sales1;

-- Correct way to show number XX.xx
ALTER TABLE sales1
MODIFY COLUMN SalesAmount DECIMAL(10,2) NOT NULL;

INSERT INTO sales1
(Store, Week, Day, SalesPerson, SalesAmount, Month)
VALUES
('London', 2, 'Monday', 'Frank', 56.25, 'May'),
('London', 5, 'Tuesday', 'Frank', 74.32, 'Sep'),
('London', 5, 'Monday', 'Bill', 98.42, 'Sep'),
('London', 5, 'Saturday', 'Bill', 73.90, 'Dec'),
('London', 1, 'Tuesday', 'Josie', 44.27, 'Sep'),
('Dusseldorf', 4, 'Monday', 'Manfred', 77.00, 'Jul'),
('Dusseldorf', 3, 'Tuesday', 'Inga', 9.99, 'Jun'),
('Dusseldorf', 4, 'Wednesday', 'Manfred', 86.81, 'Jul'),
('London', 6, 'Friday', 'Josie', 74.02, 'Oct'),
('Dusseldorf', 1, 'Saturday', 'Manfred', 43.11, 'Apr');


-- Delete whole table and datas including itself works in safe update mode
DROP TABLE sales1;
```
