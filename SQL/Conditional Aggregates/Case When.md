CASE WHEN<br>
Almost every programming language has a way to represent "if, then, else", or conditional logic. In SQL, we represent this logic with the CASE statement, as follows:
```sql
SELECT
    CASE
        WHEN elevation < 500 THEN 'Low'
        WHEN elevation BETWEEN 500 AND 1999 THEN 'Medium'
        WHEN elevation >= 2000 THEN 'High'
        ELSE 'Unknown'
    END AS elevation_tier
    , COUNT(*)
FROM airports
GROUP BY 1;
```
In the above statement, END is required to terminate the statement, but ELSE is optional. If ELSE is not included, the result will be NULL. Also notice the shorthand method of referencing columns to use in GROUP BY, so we don't have to rewrite the entire Case Statement.

**Instructions:**
Modify the case statement's such that when the elevation is less than 250, the elevation_tier column returns 'Low', when between 250 and 1749 it returns 'Medium', and when greater than or equal to 1750 it returns 'High'.

Be sure to alias the conditional statement as elevation_tier, in your query.

**My Code:**
```sql
SELECT    state, 
    COUNT(CASE WHEN elevation < 1000 THEN 1 ELSE NULL END) as count_low_elevation_aiports 
FROM airports 
GROUP BY state;
```
