## Invoking Functions

In our last exercise, we saw that when we define a function, the instructions within the code block aren’t executed. Defining a function only tells the computer to associate a name with a set of instructions. To actually execute this code we’ll need in invoke, or call, the function. Invoking a function is the process of using a function that’s been defined. Let’s look at an example:
```c#
function greetLearner()
{
  echo "Hello, Learner!\n";
  echo "I hope you're enjoying PHP!\n";
  echo "Love, Codecademy";
}

greetLearner(); 
/*
Prints:
Hello, Learner!
I hope you're enjoying PHP!
Love, Codecademy
*/
```
Below the definition of our greetLearner function, we invoked the function by writing its name followed by an opening and closing parenthesis (( )). This tells the computer to grab the instructions specified in the function definition and execute them.

When referring to functions outside of code or in comments, it’s conventional to refer to them by their name followed by parentheses (eg. greetLearner()), so we’ll be doing this from now on.

Let’s define and invoke some functions!

## Instructions

Define the function inflateEgo() which prints a compliment.

Invoke your function!

Just for kicks, edit your code so your function is invoked twice!

## My Code
```c#
<?php
// Write your code below:
  function inflateEgo(){
  echo "Dan, your voice is the best. :)\n";
}
inflateEgo();
inflateEgo();

```
