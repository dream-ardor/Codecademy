SUM(CASE WHEN )<br>
We can do that same thing for other aggregates like SUM(). For instance, if we wanted to sum the total flight distance and compare that to the sum of flight distance from a particular airline (in this case, United Airlines) by origin airport, we could run the following query:
```sql
SELECT origin, sum(distance) as total_flight_distance, sum(CASE WHEN carrier = 'UA' THEN distance ELSE 0 END) as total_united_flight_distance 
FROM flights 
GROUP BY origin;
```
**Instructions:**
Using the same pattern, find both the total flight distance and the flight distance by origin for Delta (carrier = 'DL').

Alias the flight distance as total_flight_distance and the flight distance by origin as total_delta_flight_distance.

**My Code:**
```sql
SELECT origin, sum(distance) as total_flight_distance, sum(CASE WHEN carrier = 'DL' THEN distance ELSE 0 END) as total_delta_flight_distance 
FROM flights 
GROUP BY origin;
```
