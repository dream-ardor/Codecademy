## Return Values

The value returned from a function is just that—a value. This means it can be used in any manner we would normally use a value of that type. This can take some getting used to. Take a look at the following code:
```c#
function returnFive() 
{
  return 5;
}

echo returnFive(); // Prints: 5
```
In the code above we defined a silly function, returnFive(); all it does is return the number 5. Then we used echo to print the invoked function. The way that the computer executes functions and handles their returns can take getting used to, but it’s very similar to what we experienced with numbers and variables:
```c#
echo 5 + 3; // Prints: 8

$num = 5;

echo $num + 3; // Prints: 8

echo returnFive() + 3; // Prints: 8
```
A computer evaluates 5 + 3 to 8. In the same manner, when a computer encounters a function invocation, it will execute the code in the function’s body and then evaluate to the function’s returned value. We need to think of functions as both what they do (the instructions in their code block) and what they return.

Let’s invoke more functions!

## Instructions

Use echo to print the return values of each of the three provided functions in order. The challenge: you may not use more than one line of code or more than a single statement (use only one semicolon).

Note: You can add space, new line, or other characters in between the return values.

## My Code
```c#
<?php
function first()
{
  return "You did it!\n";
}

function second()
{
  return "You're amazing!\n";
}

function third()
{
  return "You're a coding hero!\n";
}

// Write your code below:
echo first(),second(),third();

```
