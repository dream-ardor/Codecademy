## Concatenating Assignment Operator

We can assign and reassign variables to the values that result from operations:
```php
$full_name = "Aisle" . " Nevertell";
echo $full_name; // Prints: Aisle Nevertell
```
During assignment, the computer will first evaluate everything to the right of the assignment operator and return a single value.

In the code above, the computer will concatenate the strings "Aisle" and " Nevertell" into the value "Aisle Nevertell". It will then assign this string as the value to the $full_name variable.

This is true even for more complex operations:
```php
$full_name = "Aisle" . " " . "Nevertell" . " " . "Nomaderwat";
echo $full_name; // Prints: Aisle Nevertell Nomaderwat
```
One theme you may notice as you learn a programming language’s syntax is that common actions that programmers need to do a lot often have a shortcut. Consider the following:
```php
$full_name = "Aisle";
$full_name = $full_name . " Nevertell";
echo $full_name; // Prints: Aisle Nevertell
```
In the code above, we have the variable $full_name assigned the value "Aisle". We want to reassign $full_name to its current value appended with the string " Nevertell".

Believe it or not, this is such a common task that PHP offers a shorthand notation, the concatenating assignment operator (.=). Let’s compare the same action but using this alternate operator:
```php
$full_name = "Aisle";
$full_name .= " Nevertell";
echo $full_name; // Prints: Aisle Nevertell
```
It may seem funny to provide a shortcut to save just a few characters of typing, but when operations are performed often enough, those keystrokes can really add up. This syntax is also faster and easier to read which makes code easier to maintain.

One important thing to note is that even though PHP is often flexible about whitespace, it is inflexible with the concatenating assignment operator—the . and = characters must not have any spaces or other whitespace characters between them.

Let’s practice!

### Instructions

We’re going on a picnic. We started you off with the $sentence variable holding the value "\nI'm going on a picnic, and I'm taking apples".

Use the concatenating assignment operator (.=) to add another item to our list. The string you append should start with a comma(,) and a space followed by a word which starts with the letter “b”.

Next use echo to print the new value of $sentence.

That was fun. Let’s keep playing.

This time use the concatenating assignment operator (.=) to append a string which starts with a comma(,) and a space followed by a word which starts with the letter “c”.

Use echo to print the newest value of $sentence.

## My Code
```php
<?php
  echo "I'm going on a picnic!";

  $sentence = "\nI'm going on a picnic, and I'm taking apples";

  echo $sentence;

// Write your code below:

$sentence .= ", bananas";
echo $sentence;

$sentence .= ", cocktails";
echo $sentence;
```
