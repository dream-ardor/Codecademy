Union<br>
Sometimes, in order to answer certain questions based on data, we need to merge two tables together and then query the merged result. Perhaps we have two tables that contain information about products in an ecommerce store that we would like to combine.

There are two ways of doing this:

Merge the rows, called a join.
Merge the columns, called a union.
We'll focus on unions here. Union combines the result of two or more SELECT statements, using the following syntax:
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```
Each SELECT statement within the UNION must have the same number of columns with similar data types. The columns in each SELECT statement must be in the same order. By default, the UNION operator selects only distinct values.

Suppose we are a growing ecommerce store and recently acquired another store to diversify our offering. The product data still exists in two separate tables: a legacy_products table and a new_products table. To get the complete list of product names from both tables, we can perform the following union.
```sql
SELECT item_name FROM legacy_products
UNION 
SELECT item_name FROM new_products;
```

**Instructions:**
Select a complete list of brand names from the legacy_products and new_products tables.

**My Code:**
```sql
SELECT brand FROM legacy_products
UNION 
SELECT brand FROM new_products;
```
