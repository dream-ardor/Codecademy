Correlated Subqueries I<br>
Nice work! We can also write correlated subqueries in SQL.

In a correlated subquery, the subquery can not be run independently of the outer query. The order of operations is important in a correlated subquery:

A row is processed in the outer query.
Then, for that particular row in the outer query, the subquery is executed.
This means that for each row processed by the outer query, the subquery will also be processed for that row. In this example, we will find the list of all flights whose distance is above average for their carrier.
```sql
SELECT id
FROM flights AS f
WHERE distance > (
 SELECT AVG(distance)
 FROM flights
 WHERE carrier = f.carrier);
```
In the above query the inner query has to be re-executed for each flight. Correlated subqueries may appear elsewhere besides the WHERE clause, they can also appear in the SELECT.

**Instructions:**
Find the id of the flights whose distance is below average for their carrier.

**My Code:**
```sql
SELECT id
FROM flights AS f
WHERE distance < (
 SELECT AVG(distance)
 FROM flights
 WHERE carrier = f.carrier);
```
