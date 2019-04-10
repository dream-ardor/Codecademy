## String Concatenation

It can be useful to combine two strings together. This process is called string concatenation, and we can use the concatenation operator (.) to do this.

An operator is a character that performs a task in our code. The computer will take the string to the left of the concatenation operator, combine it with the string to the right, and return the resulting single string. Let’s see an example of string concatenation:
```php
echo "one" . "two"; // Prints: onetwo
```
Notice how the string “onetwo” was printed. The computer won’t make any assumptions for us—it will combine the strings exactly as they are without adding any spaces or line-breaks. If we want spaces, we’ll have to add any spaces we want ourselves. Here we added a space to the string "one ":
```php
echo "one " . "two"; // Prints: one two
```
We can also combine, or chain, our operations to get a final result:
```php
echo "one" . " " . "two" . " " . "three"; // Prints: one two three
```
The concatenation operator takes two strings (the operands) and produces a string as a result (the return value). As we delve deeper into PHP, we’ll learn about other kinds of operators. Most will take one or two operands, but there’s even one that takes three.

Let’s join some strings together!

### Instructions

Use echo to print the string "Code" concatenated to the string "cademy".

We want to learn a little more about you. Uncomment the line of code that starts with echo "\nMy name is:" and concatenate the given string with a string containing your name. Include a space after the colon without editing the string we provided.

Use echo to print a final portmanteu by concatenating these four strings "\n", "tur", "duck", and "en". Make sure to include a semicolon after the statement.

## My Code
```php
<?php
// Write your code below:   
echo "Code" . "cademy";

echo "\nMy name is:" . " Dan";
echo "\n" . "tur" . "duck" . "en";
```
