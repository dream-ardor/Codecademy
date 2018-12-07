Correlated Subqueries II<br>
It would also be interesting to order flights by giving them a sequence number based on time, by carrier.

For instance, assuming flight_id increments with each additional flight, we could use the following query to view flights by carrier, flight id, and sequence number:
```sql
SELECT carrier, id,
    (SELECT COUNT(*)
FROM flights f
WHERE f.id < flights.id
AND f.carrier=flights.carrier) + 1
 AS flight_sequence_number
FROM flights;
```
**Instructions:**
Using the same pattern, write a query to view flights by origin, flight id, and sequence number. Alias the sequence number column as flight_sequence_number.

**My Code:**
```sql
SELECT origin, id,
(SELECT COUNT(*)
FROM flights f
 WHERE f.id < flights.id
 AND f.origin=flights.origin) + 1
   AS flight_sequence_number
   FROM flights;
```
