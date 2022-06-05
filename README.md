# SQL_NewYorkRestaurants
This repo is intended to represent my SQL skill using projects provided by Codecademy.

We have put together a table of restaurants called nomnom and we need your help to answer some questions. Use the SQL commands you just learned and find the best dinner spots in the city.
The schema of this table is available here.

Tasks:

Write the following queries:
1.
Start by getting a feel for the nomnom table:
SELECT *
FROM nomnom;
What are the column names?

2.
What are the distinct neighborhoods?

3.
What are the distinct cuisine types?

4.
Suppose we would like some Chinese takeout.
What are our options?

5.
Return all the restaurants with reviews of 4 and above.

6.
Suppose Abbi and Ilana want to have a fancy dinner date.
Return all the restaurants that are Italian and $$$.

7.
Your coworker Trey can’t remember the exact name of a restaurant he went to but he knows it contains the word ‘meatball’ in it.
Can you find it for him using a query?

8.
Let’s order delivery to the house!
Find all the close by spots in Midtown, Downtown or Chinatown.

9.
Find all the health grade pending restaurants (empty values).

10.
Create a Top 10 Restaurants Ranking based on reviews.

11.
Use a CASE statement to change the rating system to:
•	review > 4.5 is Extraordinary
•	review > 4 is Excellent
•	review > 3 is Good
•	review > 2 is Fair
•	Everything else is Poor
Don’t forget to rename the new column!

Queries:

SELECT *
FROM nomnom;

SELECT DISTINCT neighborhood
FROM nomnom;

SELECT DISTINCT cuisine
FROM nomnom;

SELECT *
FROM nomnom
WHERE cuisine = 'Chinese';

SELECT *
FROM nomnom
WHERE review >= 4;

SELECT *
FROM nomnom
WHERE cuisine = 'Italian' AND price = '$$$';

SELECT name
FROM nomnom
WHERE name LIKE '%meatball%';

SELECT *
FROM nomnom
WHERE neighborhood IN ('Midtown', 'Downtown', 'Chinatown');

SELECT name
FROM nomnom
WHERE health IS NULL;

SELECT name
FROM nomnom
ORDER BY review DESC
LIMIT 10;

SELECT name,
  CASE
    WHEN review > 4.5 THEN 'Extraordinary'
    WHEN review > 4 THEN 'Excellent'
    WHEN review > 3 THEN 'Good'
    WHEN review > 2 THEN 'Fair'
    ELSE 'Poor'
  END AS 'Review'
FROM nomnom;
