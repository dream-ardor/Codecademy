Numbers<br>
Great work! Numeric functions can be used to transform numbers. Some common SQLite mathematical functions are included below that take numeric data types as inputs:

SELECT (number1 + number2);: Returns the sum of two numbers. Similar, SQL can be used for subtraction, multiplication, and division.
SELECT CAST(number1 AS REAL) / number3;: Returns the result as a real number by casting one of the values as a real number, rather than an integer.
SELECT ROUND(number, precision);: Returns the numeric value rounded off to the next value specified.
In our baked_goods table, we have information about cost designated by ingredients_cost. For accounting purposes, we'd like to make sure that each ingredient cost is rounded to four decimal places rather than two, to account for currency fluctuations.
```sql
SELECT ROUND(ingredients_cost, 4) as rounded_cost
FROM baked_goods;
```

**Instructions:**
Find the bakery's distance from the market rounded to two decimal places.

Be sure to alias the column as distance_from_market.

**My Code:**
```sql
SELECT ROUND(distance, 2) as distance_from_market
FROM bakeries;
```
