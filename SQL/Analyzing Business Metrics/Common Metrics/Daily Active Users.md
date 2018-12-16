Daily Active Users

Mineblocks is a game, and one of the core metrics to any game is the number people who play each day. That KPI is called Daily Active Users, or DAU.

DAU is defined as the number of unique players seen in-game each day. It's important not to double count users who played multiple times, so we'll use distinct in our count function.

Likewise, Weekly Active Users (WAU) and Monthly Active Users (MAU) are in the same family.

**Instructions:**
For Mineblocks, we'll use the gameplays table to calculate DAU. Each time a user plays the game, their session is recorded in gameplays. Thus, a distinct count of users per day from gameplays will give us DAU.

Calculate Daily Active Users for Mineblocks. Complete the query's count function by passing in the distinct keyword and the user_id column name.

**My Code:**
```sql
select
  date(created_at), 
  count(distinct user_id) as dau
from gameplays
group by 1
order by 1;
```
