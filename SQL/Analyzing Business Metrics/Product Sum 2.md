Product Sum 2<br>
Great! We have the sum of the the products by revenue, but we still need the percent. For that, we'll need to get the total using a subquery. A subquery can perform complicated calculations and create filtered or aggregate tables on the fly.

Subqueries are useful when you want to perform an aggregation outside the context of the current query. This will let us calculate the overall total and per-item total at the same time.

**Instructions:**
Complete the denominator in the subquery, which is the total revenue from order_items. Use the sum function to query the amount_paid from the order_items table.
```sql
select name, round(sum(amount_paid) /
  (select /**/ from order_items) * 100.0, 2) as pct
from order_items
group by 1
order by 2 desc;
```
We now have the percent or revenue each product represents!

Here order by 2 desc sorts by the second column (the percent) to show the products in order of their contribution to revenue.

**My Code:**
```sql
select name, round(sum(amount_paid) /
  (select sum(amount_paid) from order_items) * 100.0, 2) as pct
from order_items
group by 1
order by 2 desc;
```
