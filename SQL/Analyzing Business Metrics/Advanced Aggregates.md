Introduction<br>
At the heart of every great business decision is data. Since most businesses store critical data in SQL databases, a deep understanding of SQL is a necessary skill for every data analyst.

Chief among data analysis tasks is data aggregation, the grouping of data to express in summary form. We'll be working with SpeedySpoon, a meal delivery app. The folks at SpeedySpoon have asked us to look into their deliveries and help them optimize their process.

This course was developed in partnership with our good friends at Periscope Data. If you're new to SQL, we recommend you do this course first.

**Instructions:**
Complete each query by replacing the comments /**/ with SQL code.

We'll start by looking at SpeedySpoon's data. The orders table has a row for each order of a SpeedySpoon delivery. It says when the order took place, and who ordered it.

Add code to the select statement to select all columns in the orders table.
```sql
select *
from /**/
order by id
limit 100;
```
Note that the order and limit clauses keep the data organized.

The order_items table lists the individual foods and their prices in each order.

Complete the query to select all columns in the order_items table.
```sql
select * 
from /**/
order by id
limit 100;
```

**My Code:**
```sql
select *
from order_items
order by id
limit 100;
```
