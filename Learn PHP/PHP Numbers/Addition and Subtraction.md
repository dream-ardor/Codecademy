## Addition and Subtraction

PHP provides several operators we can use on numbers. Let’s start with two that are likely familiar: the addition (+) and subtraction (-) operators:
```php
echo 5 + 1; // Prints: 6
echo 6.6 + 1.2; // Prints: 7.8
echo 198263 - 263;  // Prints: 198000
echo -22.8 - 19.1; // Prints: -41.9
```
Most of the time, we don’t have to worry about which type of number we’re using. We can add a float to an integer, subtract an integer from a float, and so on.

One quirk is that operators will return integers whenever the result of the operation evaluates to a whole number. So 8.9 + 1.1 will return 10, an integer, and not 10.0 even though both of the operands in the calculation were floating point numbers.

Let’s do some adding and subtracting!

### Instructions

Use echo to print the number 12 to the terminal. The trick: use addition or subtraction to print a statement that evaluates to 12, and the number 12 can’t appear anywhere in your code!

## My Code
```php
<?php
// Write your code below:
echo 7 + 5;
```
