Non-Correlated Subqueries II<br>
Great! The query we just ran is just one kind of subquery, what we refer to as a non-correlated subquery. A non-correlated subquery is a subquery that can be run independently of the outer query and as we saw, can be used to complete a multi-step transformation.

Let's try one more non-correlated subquery. Perhaps we'd like to look at a selection of flights whose origin airport is a seaplane base, designated by SEAPLANE_BASE. The facility type of an airport is located in the fac_type field of the airports table.
```sql
SELECT * 
FROM flights 
WHERE origin in (
    SELECT code 
    FROM airports 
    WHERE fac_type = 'SEAPLANE_BASE');
```
**Instructions:**
Using the same pattern, find flight information about flights where the Federal Aviation Administration region (faa_region) is the Southern region (ASO).

**My Code:**
```sql
SELECT * 
FROM Flights
WHERE origin in (
  SELECT code
  FROM airports
  WHERE faa_region = 'ASO');
```  
  
  

