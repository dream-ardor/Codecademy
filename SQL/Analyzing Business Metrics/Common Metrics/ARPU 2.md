ARPU 2

Daily ARPU is defined as revenue divided by the number of players, per-day. To get that, we'll need to calculate the daily revenue and daily active users separately, and then join them on their dates.

One way to easily create and organize temporary results in a query is with CTEs, Common Table Expressions, also known as with clauses. The with clauses make it easy to define and use results in a more organized way than subqueries.

These clauses usually look like this:
```sql
  with {subquery_name} as (
    {subquery_body}
  )
  select ...
  from {subquery_name}
  where ...
  ```

**Instructions:**
Use a with clause to define daily_revenue and then select from it.

**My Code:**
```sql
with daily_revenue as (
  select
    date(created_at) as dt,
    round(sum(price), 2) as rev
  from purchases
  where refunded_at is null
  group by 1
)
select * from daily_revenue order by dt;
```
