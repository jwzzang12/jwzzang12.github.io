---
title: SQL Lesson Week 3
date: 2023-11-23 13:00:00 +0100
categories: [SQL, Database]
tags: [sql] # TAG names should always be lowercase
author: <author_id>
---

```sql
USE shop;
-- Find ALL sales records (and all columns) that took place in the London store, not in December, but sales concluded by Bill or Frank for the amount higher than £50
SELECT *
FROM sales1
WHERE store = 'London'
AND Month <> 'Dec'
-- AND Salesperson IN ('Bill','Frank')
AND SalesPerson = 'Bill' OR SalesPerson = 'Frank'
AND SalesAmount > 50;

-- Find out how many sales took place each week (in no particular order)
SELECT COUNT(*) as total_sales,	Week
FROM sales1
GROUP BY Week;

-- Find out how many sales took place each week AND present data by week in descending and then in ascending order
SELECT COUNT(*) as total_sales,	Week
FROM sales1
GROUP BY Week
ORDER BY Week ASC;
ORDER BY Week DESC;

-- Find out how many sales were recorded each week on different days of the week
SELECT Week, Day, COUNT(Week) AS no_of_sales
FROM sales1
GROUP BY Week, Day
ORDER BY Week ASC,
         CASE Day
             WHEN 'Monday' THEN 1
             WHEN 'Tuesday' THEN 2
             WHEN 'Wednesday' THEN 3
             WHEN 'Thursday' THEN 4
             WHEN 'Friday' THEN 5
             WHEN 'Saturday' THEN 6
             WHEN 'Sunday' THEN 7
             ELSE 8  -- Handle any other values
         END;
-- Day column is a string, it sorts lexicographically

-- We need to change salesperson's name Inga to Annette
SET SQL_SAFE_UPDATES = 0;
-- turn off Safe Mode restriction

UPDATE sales1
SET SalesPerson = 'Annett'
WHERE SalesPerson = 'Inga';

-- Find out how many sales did Annette do
SELECT COUNT(SalesPerson) as sales_Annette
FROM sales1
WHERE SalesPerson = 'Annette';

-- Find the total sales amount by each person by month
SELECT SalesPerson, Month, SUM(SalesAmount) as total_sales
FROM sales1
GROUP BY SalesPerson, Month
ORDER BY SalesPerson, Month;

-- How much (sum) each person sold for the given period
SELECT SalesPerson, SUM(SalesAmount) as total_sales
FROM sales1
GROUP BY SalesPerson
ORDER BY SalesPerson;

-- How much (sum) each person sold for the given period, including the number of sales per person, their average, lowest and highest sale amounts
SELECT SalesPerson,
	ROUND(SUM(SalesAmount),2) as total_sales,
	COUNT(SalesAmount) as sales_amount,
	ROUND(AVG(SalesAmount),2) as average_sales,
	MIN(SalesAmount) as lowest_sale, MAX(SalesAmount) as highest_sale
FROM sales1
GROUP BY SalesPerson;

-- Find the total monetary sales amount achieved by each store
SELECT Store, SUM(SalesAmount) as total_sales
FROM sales1
GROUP BY Store;

-- Find the number of sales by each person if they did less than 3 sales for the past period
SELECT SalesPerson, COUNT(SalesAmount)
FROM sales1
GROUP BY SalesPerson
HAVING COUNT(SalesPerson)<3;

-- Find the total amount of sales by month where combined total is less than £100
SELECT Month, SUM(SalesAmount) as total_sales
FROM sales1
GROUP BY Month
HAVING total_sales<100;
```
