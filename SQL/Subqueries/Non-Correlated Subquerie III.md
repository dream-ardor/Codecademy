Non-Correlated Subqueries III<br>
The non-correlated subquery examples we've used so far utilized two tables (flights and airports), but we can also perform transformations on a single table. For instance, sometimes we need to aggregate in multiple steps - like taking an average of a count.

Imagine you’d like to know how many flights there are on average, for all Fridays in a given month from the flights table. First, we’d need to calculate the number of flights per day, and then we’d need to calculate the average based on the daily flight count for each day of the week. We can do this all in one step using a subquery:
```sql
SELECT a.dep_month,
       a.dep_day_of_week,
       AVG(a.flight_count) AS average_flights
  FROM (
        SELECT dep_month,
              dep_day_of_week,
               dep_date,
               COUNT(*) AS flight_count
          FROM flights
         GROUP BY 1,2,3
       ) a
 GROUP BY 1,2
 ORDER BY 1,2;
```
The inner query provides the count of flights by day, and the outer query uses the inner query’s result set to compute the average by day of week of a given month.

**Instructions:**
Using a subquery, find the average total distance flown by day of week and month.

Be sure to alias the outer query as average_distance and the inner query as flight_distance.

**Solution:**
```sql
SELECT 
  a.dep_month, 
  a.dep_day_of_week, 
  AVG(a.flight_distance) AS average_distance 
FROM 
  (
    SELECT 
      dep_month, 
      dep_day_of_week, 
      dep_date, 
      sum(distance) AS flight_distance 
    FROM 
      flights 
    GROUP BY 
      1, 
      2, 
      3
  ) a 
GROUP BY 
  1, 
  2 
ORDER BY 
  1, 
  2;
```
