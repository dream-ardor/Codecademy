Except<br>
EXCEPT is constructed in the same way, but returns distinct rows from the first SELECT statement that aren’t output by the second SELECT statement.
```sql
SELECT column_name(s) FROM table1

EXCEPT

SELECT column_name(s) FROM table2;
```
Suppose we want to see if there are any categories that are in the new_products table that aren't in the legacy_products table. We can use an EXCEPT query to perform this analysis:
```sql
SELECT category FROM new_products

EXCEPT

SELECT category FROM legacy_products;
```
**Instructions:**
Conversely, select the items in the category column that are in the legacy_products table and not in the new_products table.

**My Code:**
```sql
SELECT category FROM legacy_products

EXCEPT

SELECT category FROM new_products;
```
