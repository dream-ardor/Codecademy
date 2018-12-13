Strings II<br>

Another useful string function in SQL is REPLACE():

REPLACE(string,from_string,to_string)
The function returns the string string with all occurrences of the string from_string replaced by the string to_string.

For example in baked_goods, there is a column named ingredients. The ingredients strings are formatted with underscores, such as baking_soda and vanilla_extract. To make these values more readable, we might like to replace the underscores with spaces. We can do so by using the following query:
```sql
SELECT id, REPLACE(ingredients,'_',' ') as item_ingredients
from baked_goods;
```
**Instructions:**
Any time enriched_flour appears in the ingredients list, we’d like to replace it with just flour. Apply this transformation and also be sure to remove the underscore in enriched_flour.

**My Code:**
```sql
SELECT REPLACE(ingredients,'enriched_flour','flour') as item_ingredients
FROM baked_goods;
```
