Daily Counts<br>

Nice work! Now that we have a good handle on our data, let's dive into some common business queries. We'll begin with the Daily Count of orders placed. To make our Daily Count metric, we'll focus on the date function and the ordered_at field.

To get the Daily Metrics we need the date. Most dates in databases are timestamps, which have hours and minutes, as well as the year, month, and day. Timestamps look like 2015-01-05 14:43:31, while dates are the first part: 2015-01-05.

We can easily select the date an item was ordered at with the date function and the ordered_at field:
```sql
select date(ordered_at)
from orders;
```
**Instructions:**
Let's get a Daily Count of orders from the orders table. Complete the query using the date function to cast the timestamps in ordered_at to dates.
```sql
select /**/
from orders
order by 1
limit 100;
```
The order by 1 statement is a shortcut for order by date(ordered_at). The 1 refers to the first column.

**My Code:**
```sql
select date(ordered_at)
from orders
order by 1
limit 100;
```
