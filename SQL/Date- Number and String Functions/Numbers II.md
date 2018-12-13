Numbers II
A couple more useful numeric SQL functions are included below: MAX and MIN.

MAX(n1,n2,n3,...): returns the greatest value in the set of the input numeric expressions MIN(n1,n2,n3,...): returns the least value in the set of the input numeric expressions

In our baked_goods table, in addition to the numeric ingredients_cost we have information about the packaging cost located in the packaging_cost column. We can use the MAX function to determine the overall greatest value of cost for each item using the following query:
```sql
SELECT id, MAX(ingredients_cost, packaging_cost)
FROM baked_goods;
```

**Instructions:**
We also have information about cook time designated as cook_time and cool down time designated as cool_down_time in the baked_goods table. Find the greatest time value for each item in the table.

**My Code:**
```sql
SELECT id, MAX(cook_time, cool_down_time)
FROM baked_goods;
```
