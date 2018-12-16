Daily Revenue<br>

We have the Daily Count of orders, but what we really want to know is revenue. How much money has SpeedySpoon made from orders each day?

**Instructions:**
We can make a few changes to our Daily Count query to get the revenue.

First, instead of using count(1) to count the rows per date, we'll use round(sum(amount_paid), 2) to add up the revenue per date. Complete the query by adding revenue per date.

Second, we need to join in the order_items table because that table has an amount_paid column representing revenue. Complete the query by adding a join clause where orders.id = order_items.order_id.

Note that the round function rounds decimals to digits, based on the number passed in. Here round(..., 2) rounds the sum paid to two digits.

Nice. Now with a small change, we can find out how much we're making per day for any single dish. What's the daily revenue from customers ordering kale smoothies?

Complete the query by using a where clause to filter the daily sums down to orders where the name = 'kale-smoothie'.

**My Code:**
```sql
select date(ordered_at), round(sum(amount_paid), 2)
from orders
 join order_items on
 orders.id = order_items.order_id
where name = 'kale-smoothie'
group by 1
order by 1;
```

