Daily Active Users 2

Great! Since Mineblocks is on multiple platforms, we can calculate DAU per-platform.

**Instructions:**
Previously we calculated DAU only per day, so the output we wanted was [date, dau_count]. Now we want DAU per platform, making the desired output [date, platform, dau_count].

Calculate DAU for Mineblocks per-platform. Complete the query below. You will need to select the platform column and add a count function by passing in the distinct keyword and the user_id column name.

**My Code:**
```sql
select
  date(created_at), 
 platform,
  count(distinct user_id) as dau
from gameplays
group by 1, 2
order by 1, 2;
```
