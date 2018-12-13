Generalizations<br>

Congratulations! You just learned about date, number, and string functions in SQL. What can we generalize so far?

Date Functions:

* DATETIME; Returns the date and time of the column specified. This can be modified to return only the date or only the time.
* DATETIME(time1, +X hours, Y minutes, Z days): Increments the specificed column by a given number of hours, minutes, or days.

Numeric Functions:

* (number1 + number2);: Returns the sum of two numbers, or other mathematical operations, accordingly.
* CAST(number1 AS REAL) / number2;: Returns the result as a real number by casting one of numeric inputs as a real number
* ROUND(number, precision);: Returns the numeric value rounded off to the next value specified.

String Functions:

* 'string1' || ' ' || 'string2';: Concatenates string1 and string 2, with a space between.
* REPLACE(string,from_string,to_string): Returns the string with all occurrences of the string from_string replaced by the string to_string.
