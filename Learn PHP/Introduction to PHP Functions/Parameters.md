## Parameters

Functions that do exactly the same thing every time they run can save us from having to repeat code in our programs, but functions can do more.

In the beginning of this lesson, we wrote a greetLearner() function that printed the same friendly greeting every time it was invoked. That’s ok… we guess… But what we’d really like is to print a customized greeting. We can accomplish this by using parameters!

When we define a function, we can also define parameters. A parameter is a variable which serves as a placeholder throughout the function’s code block. When the function is invoked, it’s invoked with a specific value. As the computer executes the function, it replaces each occurrence of the parameter with the value that was passed in. The actual value passed in is known as an argument.

Let’s look at an example:
```php
function sayCustomHello($name)
{
echo "Hello, $name!";
};

sayCustomHello("Aisle Nevertell"); // Prints: Hello, Aisle Nevertell!

sayCustomHello("Codecademy learner"); // Prints: Hello, Codecademy Learner!
```
In the code above, we defined the sayCustomHello() function. It has a $name parameter. We invoked the function twice:

The first time, we passed in "Aisle Nevertell" as the argument. During that invocation, the function assigned "Aisle Nevertell" to $name so Hello, Aisle Nevertell! was printed.

The second time we invoked the function with the argument "Codecademy learner" so $name was assigned that value and Hello, Codecademy Learner! was printed.

Let’s get some parameter practice!

## Instructions

Write a function increaseEnthusiasm() which takes in a string parameter and returns that string appended with an exclamation mark.

Use echo to print the result of invoking your increaseEnthusiasm() function with a string of your choice.

Write a function repeatThreeTimes() which takes in a string parameter and returns that string repeated three times (without introducing characters which didn’t appear in the original string).

Use echo to print the result of invoking your repeatThreeTimes() function with a string of your choice.

Ready for a little trickiness? Use echo to print the result of invoking your increaseEnthusiasm() with the result of invoking repeatThreeTimes() as the argument passed into increaseEnthusiasm(). You can choose any string you like for the argument to repeatThreeTimes().

## My Code
```php
<?php
// Write your code below:
function increaseEnthusiasm($str) {
  return $str . "!";
}

echo increaseEnthusiasm("Let's have fun");

function repeatThreeTimes($str) {
  return $str . $str . $str;
}
echo repeatThreeTimes("Can we cook now?\n");


```
