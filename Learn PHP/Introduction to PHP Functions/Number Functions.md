## Number Functions

Another common task in programming is working with numbers, so it shouldn’t surprise us that PHP comes with some handy built-in functions for working with numbers.

The abs() function returns the absolute value of its number argument:
```php
echo abs(-10.99); // Prints: 10.99

echo abs(127); // Prints: 127
```
Another useful function is the round() function which returns the nearest integer to its number argument:
```php
echo round(1.2); // Prints 1

echo round(1.5); //Prints 2

echo round(1298736.821763876); // Prints: 1298737
```
Let’s practice!

## Instructions

You’re going to write a function which uses the abs() built-in function within its definition.

Write a function called calculateDistance() that calculates the distance between two numbers. The function should return the same result for two arguments no matter what order they’re passed into the function.

Here are some examples of how the function should work:
```php
calculateDistance(-1, 4) should return 5
calculateDistance(4, -1) should return 5
calculateDistance(3, 7) should return 4
calculateDistance(7, 3) should return 4
```
Once you’ve finished writing your function, you should run it to make sure it’s working how it should.

Check out the hint if you want some help on the strategy or a reminder about how to define your own functions.

Awesome! This time you’re going to write a function which uses the round() function.

Write a function calculateTip() which takes a number representing the total cost of a meal as its argument.

Your function should calculate a new total with an 18% tip added and return that value rounded to the nearest integer.

You’re function must invoke the built-in round() function. For example:
```php
calculateTip(100) should return 118
calculateTip(35) should return 41
calculateTip(88.77) should return 105
```

## My Code
```php
<?php
namespace Codecademy;

// Write your code below:

function calculateDistance($a,$b){
  return abs($a - $b);
};

function calculateTip($cost){
  return round($cost * 1.18);
  
};

echo calculateDistance(10,6);

```
