1 Day Retention 2

Before we can calculate retention we need to get our data formatted in a way where we can determine if a user returned.

Currently the gameplays table is a list of when the user played, and it's not easy to see if any user came back.

By using a self-join, we can make multiple gameplays available on the same row of results. This will enable us to calculate retention.

The power of self-join comes from joining every row to every other row. This makes it possible to compare values from two different rows in the new result set. In our case, we'll compare rows that are one date apart from each user.

**Instructions:**
To calculate retention, start from a query that selects the date(created_at) as dt and user_id columns from the gameplays table.

Now we'll join gameplays on itself so that we can have access to all gameplays for each player, for each of their gameplays.

This is known as a self-join and will let us connect the players on Day N to the players on Day N+1. In order to join a table to itself, it must be aliased so we can access each copy separately.

We aliased gameplays in the query above because in the next step, we need to join gameplays to itself so we can get a result selecting [date, user_id, user_id_if_retained].

Complete the query by using a join statement to join gameplays to itself on user_id using the aliases g1 and g2.

We don't use the using clause here because the join is about to get more complicated.

**My Code:**
```sql
select
  date(g1.created_at) as dt,
  g1.user_id
from gameplays as g1
  join gameplays as g2 on
    g1.user_id = g2.user_id
order by 1
limit 100;
```
