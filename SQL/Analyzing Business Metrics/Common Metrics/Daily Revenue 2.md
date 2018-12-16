Daily Revenue 2

Great! That query doesn't take refunds into account. We'll update the query to exclude refunds.

Fields like refunded_at will only have data if the transaction was refunded, and otherwise left null.

**Instructions:**
Update our daily revenue query to exclude refunds.

Complete the query by filtering for refunded_at is null.

**My Code:**
```sql
select
  date(created_at),
  round(sum(price), 2) as daily_rev
from purchases
where refunded_at is null
group by 1
order by 1;
```
