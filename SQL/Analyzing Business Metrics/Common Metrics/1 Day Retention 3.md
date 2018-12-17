1 Day Retention 3

Now that we have our gameplays table joined to itself, we can start to calculate retention.

1 Day Retention is defined as the number of players who returned the next day divided by the number of original players, per day. Suppose 10 players played Mineblocks on Dec 10th. If 4 of them play on Dec 11th, the 1 day retention for Dec 10th is 40%.

**Instructions:**
The previous query joined all rows in gameplays against all other rows for each user, making a massive result set that we don't need.

We'll need to modify this query.
```sql
select
  date(g1.created_at) as dt,
  g1.user_id,
  g2.user_id
from gameplays as g1
  join gameplays as g2 on
    g1.user_id = g2.user_id
    and /**/
order by 1
limit 100;
```
Complete the query above such that the join clause includes a date join:

date(g1.created_at) = date(datetime(g2.created_at, '-1 day'))
This means "only join rows where the date in g1 is one less than the date in g2", which makes it possible to see if users have returned!

The query above won't return meaningful results because we're using an inner join. This type of join requires that the condition be met for all rows, effectively limiting our selection to only the users that have returned.

Instead, we want to use a left join, this way all rows in g1 are preserved, leaving nulls in the rows from g2 where users did not return to play the next day.

Change the join clause to use left join and count the distinct number of users from g1 and g2 per date.
```sql
select
  date(g1.created_at) as dt,
  count(distinct g1.user_id) as total_users,
  count(distinct g2.user_id) as retained_users
from gameplays as g1
  /**/ gameplays as g2 on
    g1.user_id = g2.user_id
    and date(g1.created_at) = date(datetime(g2.created_at, '-1 day'))
group by 1
order by 1
limit 100;
```
**My Code:**
```sql
select
  date(g1.created_at) as dt,
  count(distinct g1.user_id) as total_users,
  count(distinct g2.user_id) as retained_users
from gameplays as g1
  left join gameplays as g2 on
    g1.user_id = g2.user_id
    and date(g1.created_at) = date(datetime(g2.created_at, '-1 day'))
group by 1
order by 1
limit 100;
```
