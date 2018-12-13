Dates II<br>
Nice work! Now let's assume that we have a column in our baked_goods table named manufacture_time in the format YYYY-MM-DD hh:mm:ss.

We'd like to know the number of baked_goods manufactured by day, and not by second. We can use the DATE() function to easily convert timestamps to dates and complete the following query:
```sql
SELECT DATE(manufacture_time), count(*) as count_baked_goods
FROM baked_goods
GROUP BY DATE(manufacture_time);
```
Similarly, we can query the time with
```sql
SELECT TIME(manufacture_time), count(*) as count_baked_goods
FROM baked_goods
GROUP BY TIME(manufacture_time);
```
**Instructions:**
Find the number of baked goods by date of delivery.

Be sure to alias the total count of baked goods as count_baked_goods

**My Code:**
```sql
SELECT DATE(delivery_time), count(*) as count_baked_goods
FROM baked_goods
GROUP BY DATE(delivery_time);
```
