## Mathematical Assignment Operators

One common task when manipulating number variables is to reassign them to their old value with some operation performed on it.
```php
$savings = 800;
$bike_cost = 75;
$savings = $savings - $bike_cost;
echo $savings; // Prints: 725
```
This is such a common task that PHP provides a shorter syntax using arithmetic assignment operators:

Operation:	Long Syntax:	Short Syntax:
Add	$x = $x + $y	$x += $y
Subtract	$x = $x - $y	$x -= $y
Multiply	$x = $x * $y	$x *= $y
Divide	$x = $x / $y	$x /= $y
Mod	$x = $x % $y	$x %= $y

We could use this shorter syntax to rewrite the above code:
```php
$savings = 800;
$bike_cost = 75;
$savings -= $bike_cost;
echo $savings; // Prints: 725
```
With mathematical assignment operators, PHP doesn’t allow spaces between the two characters.

Those keystrokes can add up, so let’s practice using arithmetic assignment operators on variables!

### Instructions

We’re going to do a mathematical “magic” trick. Create a variable, $my_num and assign as its value any number.

Next, create a second variable, $answer and assign $my_num as its value.

Use the addition assignment operator to add 2 to $answer.

Use the multiplication assignment operator to multiply $answer by 2.

Use the subtraction assignment operator to subtract 2 from $answer.

Use the division assignment operator to divide $answer by 2.

Almost there. Use the subtraction assignment operator to subtract your original number ($my_num) from $answer. Finally, use echo to print $answer to the terminal.

If everything went as it should, $answer should be 1. No matter what your original number was! Don’t belive us? Go ahead try it with a different number for the value of $my_num.

## My Code
```php
<?php
// Write your code below:

$my_num = 69;
$answer = $my_num;
$answer += 2;
$answer *= 2;
$answer -= 2;
$answer /= 2;
$answer -= $my_num;
echo $answer;
```
