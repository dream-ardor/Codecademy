## Finding Functions

In order to find out about built-in functions (and other language features), you’ll want to get comfortable exploring the PHP documentation. The docs can get a little overwhelming—for example, this seemingly infinite index of PHP functions is pretty unwieldy.

The documentation contains some lists organized by topic: this is a list of PHP string functions and this is a list of math functions.

It’s often faster to use Google to navigate to the right part of the official documentation (php.net). For example, when I googled “PHP absolute value” the first result was a link to the abs() function in the PHP documentation.

Let’s practice discovering new functions!

## Instructions

In the following tasks, you’ll be defining functions which call built-in functions within their function bodies. This time, however, you’ll have to search for the correct built-in function.

Write a function convertToShout() which takes in a string as its argument and returns that string converted to all capital letters and appended with an exclamation point. You should use a specific built-in function to do this conversion.

Once you’ve finished writing your function, you should run it—using echo to see its output—to make sure it’s working how it should.

Here are some examples:

* convertToShout("woah there, buddy") should return "WOAH THERE, BUDDY!"
* convertToShout("i just don't know") should return "I JUST DON'T KNOW!"
* convertToShout("oh, ok, that's fine") should return "OH, OK, THAT'S FINE!"
* convertToShout("it's nice to meet you") should return "IT'S NICE TO MEET YOU!"

Create a function tipGenerously() which takes in a number argument, representing the cost of a meal and returns the number with a 20% tip added rounded up to the nearest integer. You should use a specific built-in function to achieve this rounding.

Once you’ve finished writing your function, you should run it—using echo to see its output—to make sure it’s working how it should.

Here are some examples:

* tipGenerously(100.00) should return 120
* tipGenerously(982.27) should return 1179
* tipGenerously(15.67) should return 19
* tipGenerously(66.18) should return 80
* tipGenerously(21.65) should return 26

Create a function calculateCircleArea() which takes in a circle’s diameter and returns its area. You need to use a built-in function to achieve the exact precision of Pi we’re looking for.

Once you’ve finished writing your function, you should run it—using echo to see its output—to make sure it’s working how it should.

Here are some examples:

* calculateCircleArea(25) should return 490.87385212341
* calculateCircleArea(30) should return 706.8583470577
* calculateCircleArea(872) should return 597204.19707681
* calculateCircleArea(6) should return 28.274333882308
* calculateCircleArea(29) should return 660.51985541725

## My Code
```php
<?php
namespace Codecademy;

// Write your code below:
function convertToShout($str){
  return strtoupper($str) . "!";
};

echo convertToShout("hey there");


function tipGenerously($num){
  return ceil($num * 1.2);
}
echo "\n";
echo tipGenerously(8);

function calculateCircleArea($di){
  return pi() * ($di/2)**2;
}

echo "\n";
echo calculateCircleArea(25);

```
