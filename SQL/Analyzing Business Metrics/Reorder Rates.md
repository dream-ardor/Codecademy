Reorder Rates

While we do know that kale smoothies (and drinks overall) are not driving a lot of revenue, we don't know why. A big part of data analysis is implementing your own metrics to get information out of the piles of data in your database.

In our case, the reason could be that no one likes kale, but it could be something else entirely. To find out, we'll create a metric called reorder rate and see how that compares to the other products at SpeedySpoon.

We'll define reorder rate as the ratio of the total number of orders to the number of people making those orders. A lower ratio means most of the orders are reorders. A higher ratio means more of the orders are first purchases.

**Instructions:**
Let's calculate the reorder ratio for all of SpeedySpoon's products and take a look at the results. Counting the total orders per product is straightforward. We count the distinct order_ids in the order_items table.

Complete the query by passing in the distinct keyword and the order_id column name into the count function

**My Code:**
```sql
select name,count(distinct order_id)
from order_items
group by 1
order by 1;
```
Now we need the number of people making these orders.

To get that information, we need to join in the orders table and count unique values in the delivered_to field, and sort by the reorder_rate.

Complete the query below. The numerator should count the distinct order_ids. The denominator should count the distinct values of the orders table's delivered_to field (orders.delivered_to).

**My Code:**
```sql
select name, round(1.0 * count(distinct order_id) /
  count(distinct delivered_to), 2) as reorder_rate
from order_items
  join orders on
    orders.id = order_items.order_id
group by 1
order by 2 desc;
```

