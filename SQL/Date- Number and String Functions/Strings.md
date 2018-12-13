Strings<br>
String manipulation can be useful to derive information from columns. We'll cover a couple of the common string functions here.

A common use case for string manipulation in SQL is concatenation of strings. In SQLite, this is written as
```sql
SELECT string1 || ' ' || string2;
```
For example, the bakeries table contains both city and state columns. In order to create a route for these columns, we use the || function to concatenate them as in the following query:
```sql
SELECT city || ' ' || state as location
FROM bakeries;
```
String functions are again, very database specific, and it is best practice to consult documentation before proceeding.

**Instructions:**
Combine the first_name and last_name columns from the bakeries table as the full_name to identify the owners of the bakeries.

Be sure to add a space between the names in the full_name as shown in the example.

**My Code:**
```sql
SELECT first_name || ' ' || last_name as full_name
FROM bakeries;
```
