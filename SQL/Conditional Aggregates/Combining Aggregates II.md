Combining aggregates II<br>

Modify the previous elevation example to find the percentage of high elevation airports (elevation >= 2000) by state.

**Instructions:**
Find the percentage of high elevation airports (elevation >= 2000) by state from the airports table.

In the query, alias the percentage column as percentage_high_elevation_airports.

**Solution:**
```sql
SELECT state, 100.0 * sum(CASE WHEN elevation >= 2000 THEN 1 ELSE 0 END) / count(*)  as percentage_high_elevation_airports FROM airports GROUP BY state;
```
