Intersect<br>
INTERSECT is used to combine two SELECT statements, but returns rows only from the first SELECT statement that are identical to a row in the second SELECT statement. This means that it returns only common rows returned by the two SELECT statements.
```sql
SELECT column_name(s) FROM table1

INTERSECT

SELECT column_name(s) FROM table2;
```
For instance, we might want to know what brands in our newly acquired store are also in our legacy store. We can do so using the following query:
```sql
SELECT brand FROM new_products

INTERSECT

SELECT brand FROM legacy_products;
```
**Instructions:**
Select the items in the category column that are both in the newly acquired new_products table and the legacy_products table.

**My Code:**
```sql
SELECT category FROM legacy_products

INTERSECT

SELECT category FROM new_products;
```
