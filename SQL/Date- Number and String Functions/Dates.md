Dates
We'll begin with dates. Dates are often written in the following format

1. Date: YYYY-MM-DD

2. Datetime or Timestamp: YYYY-MM-DD hh:mm:ss

We can use SQL's date functions to transform data into a desired format. Since date functions can be database specific, verify the functions that exist on your relational database management system.

For example, this statement
```sql
SELECT DATETIME(manufacture_time)
FROM baked_goods;
```
Would return the date and time for the manufacture_time column.

**Instructions:**
Using the datetime function, select the date and time of all deliveries in the baked_goods table using the column delivery_time.

**My Code:**
```sql
SELECT DATETIME(delivery_time)
FROM baked_goods;
```
