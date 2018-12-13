Combining aggregates<br>
Oftentimes we'd like to combine aggregates, to create percentages or ratios.

In the instance of the last query, we might want to find out the percent of flight distance that is from United by origin airport. We can do this simply by using the mathematical operators we need in SQL:
```sql
SELECT     origin, 
    100.0*(sum(CASE WHEN carrier = 'UN' THEN distance ELSE 0 END)/sum(distance)) as percentage_flight_distance_from_united FROM flights 
GROUP BY origin;
```
**Instructions:**
Using the same pattern, find the percentage of flights from Delta by origin (carrier = 'DL')

In the query, alias the column as
```sql
percentage_flight_distance_from_delta
```
**My Code:**
```sql
SELECT     origin, 
    100.0*(sum(CASE WHEN carrier = 'DL' THEN distance ELSE 0 END)/sum(distance)) as percentage_flight_distance_from_delta FROM flights 
GROUP BY origin;
```
