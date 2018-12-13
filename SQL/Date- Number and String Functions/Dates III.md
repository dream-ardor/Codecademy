Dates III<br>

Given a datepart and a column of date or timestamp data type, we can increment date or timestamp values by a specified interval.

For example, in SQLite, the statement
```sql
DATETIME(time1, '+3 hours', '40 minutes', '2 days');
```
Would return a time 3 hours, 20 minutes, and 2 days after time1.

Imagine that each dessert in our baked_goods table is inspected 2 hours, 30 minutes, and 1 day after the manufacture time. To derive the inspection date for each baked good, we can use the following query
```sql
SELECT DATETIME(manufacture_time, '+2 hours', '30 minutes', '1 day') as inspection_time
FROM baked_goods;
```
**Instructions:**
Each of the baked goods is packaged by Baker's Market exactly five hours, twenty minutes, and two days after the delivery (designated by delivery_time). Create a query returning all the packaging times for the goods in the baked_goods table

Be sure to alias the package time column as package_time.

**My Code:**
```sql
SELECT DATETIME(delivery_time, '+5 hours', '20 minutes', '2 day') as package_time
FROM baked_goods;
```
