## Defining Functions

Let’s get right to it and create our first function:
```c#
function greetLearner()
{
  echo "Hello, Learner!\n";
  echo "I hope you're enjoying PHP!\n";
  echo "Love, Codecademy";
}
```
Let’s walk through the code above:

* We used the function keyword to start our function definition.
* We named the function greetLearner. Function names must start with a letter or underscore, followed by any number of letters, numbers, or underscores.
* We created a code block with curly brackets ({ }). The code inside this code block will execute when our function is invoked.
* Within that block we wrote three instructions: echo "Hello, Learner!\n!";, echo "I hope you're enjoying PHP!\n";, and echo "Love, Codecademy";
* With our greetLearner() function defined, we’ll be able to invoke the function multiple times and print those strings without having to copy or retype the three echo statements again and again.

A few notes on naming conventions: we typically snake case (separate words with underscores) our variable names, but, in order to easily tell the difference between variables and functions in our code, we’ll do something different when naming functions. We’re going to use camel case for our function names—we’ll start with a lowercase letter and then capitalize the first letter of every new word: camelCase vs. snake_case. Another good practice is to name functions in a way that describes what they do—typically we’ll start function names with a verb.

In the next exercise, we’ll show you how to invoke a function. For now, let’s get some practice defining them!

## Instructions

Define a function named praisePHP. You can leave the function body blank for now.

Add at least one echo statement inside your function body which prints a string praising the PHP language.

Now that your function is fully defined, run your program. Notice what happens… or really what doesn’t happen.

## My Code
```c#
<?php
// Write your code below:
  function praisePHP(){
  echo "Praise the PHP gods!";
}

```
