DATE, NUMBER, AND STRING FUNCTIONS<br>

Date, Time and String Functions
Oftentimes, data in columns of tables is not in the exact format we need to complete our desired analysis. We may need to extract a date from a full timestamp, manipulate a number, or combine first and last name columns to create a full name.

In this lesson, we'll be learning about some of SQL's built-in functions for transforming dates, numbers and strings. We'll be using database of bakeries in this lesson.

It is important to note that date, number, and string functions are highly database dependent. Here, we focus on built-in functions in the SQLite database management system.

**Instructions:**
Select ten rows from the bakeries table.

**My Code:**
```sql
SELECT *
FROM bakeries
LIMIT 10;
```
