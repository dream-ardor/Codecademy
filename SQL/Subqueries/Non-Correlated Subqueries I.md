Non-Correlated Subqueries I<br>
Nice work! Let's continue with subqueries.

Imagine that you are the head of air traffic control. In our airplanes database, you'd like to know which flights had an origin airport with an elevation greater than 2000 feet. We can do this with a subquery.

We first create an inner query, or subquery, that finds the airports with elevation greater than 2000 from the airports table:
```sql
SELECT code 
  FROM airports 
  WHERE elevation > 2000;
  ```
Next, we take the result set of the inner query and use it to filter on the flights table, to find the flight detail that meets the elevation criteria.
```sql
SELECT * 
FROM flights 
WHERE origin in (
    SELECT code 
    FROM airports 
    WHERE elevation > 2000);
```
As shown above, a subquery is nested within another query to give us our desired result.

**Instructions:**
Using the same pattern from the example above, find flight information about flights where the origin elevation is less than 2000 feet.

**My Code:**
```sql
SELECT * 
FROM Flights
WHERE origin in (
  SELECT code
  FROM airports
  WHERE elevation < 2000); 
```
