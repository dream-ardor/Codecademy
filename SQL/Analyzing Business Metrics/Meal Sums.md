Meal Sums<br>

It looks like the smoothies might not be performing well, but to be sure we need to see how they're doing in the context of the other order items.

We'll look at the data several different ways, the first of which is determining what percent of revenue these smoothies represent.

**Instructions:**
To get the percent of revenue that each item represents, we need to know the total revenue of each item. We will later divide the per-item total with the overall total revenue.

The following query groups and sum the products by price to get the total revenue for each item. Complete the query by passing in sum(amount_paid) into the round function and rounding to two decimal places.

**My Code:**
```sql
select name, round(sum(amount_paid), 2)
from order_items
group by name
order by 2 desc;
```
