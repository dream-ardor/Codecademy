Daily Average Revenue Per Purchasing User

We've looked at DAU and Daily Revenue in Mineblocks. Now we must understand the purchasing habits of our users.

Mineblocks, like every freemium game, has two types of users:

* purchasers: users who have bought things in the game
* players: users who play the game but have not yet purchased

The next KPI we'll look at Daily ARPPU - Average Revenue Per Purchasing User. This metric shows if the average amount of money spent by purchasers is going up over time.

Daily ARPPU is defined as the sum of revenue divided by the number of purchasers per day.

**My Code:**
```sql
select
  date(created_at),
  round(sum(price) / count(distinct user_id), 2) as arppu
from purchases
where refunded_at is null
group by 1
order by 1;
```
