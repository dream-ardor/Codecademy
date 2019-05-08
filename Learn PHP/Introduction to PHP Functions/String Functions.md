## String Functions

We can find PHP built-in functions to accomplish common tasks. Need to reverse a string? There’s a built-in function for that!

The strrev() function takes in a string as its argument and returns a string with all of the characters of the original string in reverse order.

Let’s see it in action:
```php
echo strrev("Hello, World!"); // Prints: !dlroW ,olleH
```
Remember that we can use the values returned from functions directly (rather than saving them into variables). In the code above, we used echo to print the value returned from invoking the strrev() function with the string "Hello, World!" as its argument.

PHP also comes with built-in functions to change the capitalization of a string. We can use the strtolower() function to transform an argument string into all lowercase letters:
```php
echo strtolower("HeLLo"); // Prints: hello
```
Built-in functions often have multiple parameters. The str_repeat() function takes a string as its first argument and a number as its second. It returns a string containing the argument string repeated the argument number of times.
```php
echo str_repeat("hi", 10); // Prints: hihihihihihihihihihi 
```
In the above code we used echo to print the value returned from invoking str_repeat() with "hi" and 10 as its arguments—"hihihihihihihihihihi" .

Let’s practice!

## Instructions

Use echo and the strrev() function to print the following string reversed: ".pu ti peeK .taerg gniod er'uoY"

Use echo and the strtolower() function to print the following string with all lowercase letters: "SOON, tHiS WILL Look NoRmAL."

Use echo and the str_repeat() function to print the string "\nThere's no place like home.\n" three times.

## My Code
```php
<?php
namespace Codecademy;

// Write your code below:

echo strrev(".pu ti peeK .taerg gniod er'uoY");
echo strtolower("SOON, tHiS WILL Look NoRmAL.");
echo str_repeat("\nThere's no place like home.\n",3);
```
