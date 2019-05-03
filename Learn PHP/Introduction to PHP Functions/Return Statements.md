## Return Statements

As we build more complicated functions, we’ll often be using them to process data. In order for the data to be useful, functions have the ability to return a value in addition to performing instructions. Let’s look at an example:
```c#
function countdown() 
{
  echo "4, 3, 2, 1, ";
  return "blastoff!";
}
```
When the countdown() function is invoked it will print 4, 3, 2, 1,, but what about the string "blastoff!"? This value will be returned. We have a lot of options for what to do with a returned value. For example, we could capture it in a variable:
```c#
$return_value = countdown(); // Prints: 4, 3, 2, 1, 
echo $return_value; // Prints: blastoff!
```
This example is a little silly, since we could have just printed the string within the function, but, as we continue to create more complicated functions, the ability to return a value will become extremely useful.

Let’s get some practice returning a value from a function!

## Instructions

Write a function printStringReturnNumber() which prints a string and returns a number value.

Capture your function’s return value in a variable named $my_num.

Use echo to print your $my_num variable.

## My Code
```c#
<?php

// Write your code below:
  function printStringReturnNumber(){
  echo "Dan is the best!";
  return 69;
}

$my_num = printStringReturnNumber();
echo $my_num;
```
