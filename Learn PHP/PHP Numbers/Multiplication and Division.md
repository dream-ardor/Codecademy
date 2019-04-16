## Multiplication and Division

PHP also gives us operators for performing multiplication (*) and division (/).
```php
echo 2 * 3; // Prints: 6
echo -21 / 7; // Prints: -3
```
Like with addition and subtraction, when we perform multiplication or division, the computer will return an integer whenever the operation evaluates to a whole number.

The reverse is also true:
```php
$num_cookies = 24;
$num_friends = 7;
$cookies_per_friend = $num_cookies / $num_friends;
echo $cookies_per_friend; // Prints: 3.4285714285714
```
In the code above, we performed an operation on two integers that didn’t divide into each other evenly, so the computer returned a floating point number.

Let’s multiply and divide!

### Instructions

Meg is trying to figure out how long, on average it takes her to learn a programming language. So far, she knows Ruby, Python, JavaScript, and C++. Create a variable, $num_languages, and assign to it the number of programming languages she has learned. Create a second variable, $months and assign 11 to it, which is the number of months she’s spent learning how to code.

Let’s get more precise. Meg realizes that she hasn’t quite studied every day. Create a variable $days and assign as its value the result of multiplying $months by the number of days per month she thinks she actually spent studying, which is 16 days each month.

Let’s figure out, on average, how many days it took her to learn each language. Assign the result of of this operation to a variable $days_per_language.

Print your $days_per_language variable to the terminal.

## My Code
```php
<?php
// Write your code below:
$num_languages = 4;
$months = 11;

$days = $months * 16;
$days_per_language = $days / $num_languages ;

echo $days_per_language;

```
