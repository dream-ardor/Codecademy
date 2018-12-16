Daily Revenue

At the heart of every company is revenue, and Mineblocks is no exception. For our first KPI we'll calculate daily revenue.

**Instructions:**
Daily Revenue is simply the sum of money made per day.

To get close to Daily Revenue, we calculate the daily sum of the prices in the purchases table. Complete the query by using the sum function and passing the price column from the purchases table.

**My Code:**
```sql
select
date(created_at),
round(sum(price), 2)
from purchases
group by 1
order by 1;
```
