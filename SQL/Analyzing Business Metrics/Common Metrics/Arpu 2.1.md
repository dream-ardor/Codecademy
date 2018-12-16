ARPU 2

Great! Now you're familiar with using the with clause to create temporary result sets.

You just built the first part of ARPU, daily_revenue. From here we can build the second half of ARPU in our with clause, daily_players, and use both together to create ARPU.

**Instructions:**
Now that we have the revenue and DAU, join them on their dates and calculate daily ARPU. Complete the query by adding the keyword using in the join clause.

**My Code:**
```sql
with daily_revenue as (
  select
    date(created_at) as dt,
    round(sum(price), 2) as rev
  from purchases
  where refunded_at is null
  group by 1
),
daily_players as (
  select
    date(created_at) as dt,
    count(distinct user_id) as players
  from gameplays
  group by 1
)
select
  daily_revenue.dt,
  daily_revenue.rev / daily_players.players
from daily_revenue
  join daily_players using (dt);
```
