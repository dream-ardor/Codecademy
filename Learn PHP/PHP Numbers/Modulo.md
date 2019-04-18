## Modulo

PHP also provides an operator that might be less familiar: modulo (%). The modulo operator returns the remainder after the left operand is divided by the right operand.
```php
echo 7 % 3; // Prints: 1
```
In the code above, 7 % 3 returns 1. Why? We’re trying to fit 3 into 7 as many times as we can. 3 fits into 7 at most twice. What’s left over—the remainder—is 1, since 7 minus 6 is 1.

The modulo operator will convert its operands to integers before performing the operation. This means 7.9 % 3.8 will perform the same calculation as 7 % 3—both operations will return 1.

Let’s look at another example of the modulo operator in action:
```php
$num_cookies = 27;
$cookies_per_serving = 4;
$leftover_cookies = $num_cookies % $cookies_per_serving;
echo $leftover_cookies; // Prints: 3
```
Let’s practice using modulo!

### Instructions

We have 82 students going on a class trip. We want to divide the students into groups of 6. Use the modulo operator to echo how many students will be left without groups.

## My Code
```php
<?php
// Write your code below:
  
  echo 82 % 6;

```
