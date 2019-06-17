## If Statements

Conditional statements are the most commonly used control structures in programming. They rely on the computer being able to reason whether conditions are true or false.

The most basic conditional statement is if if statement. An if statement executes a block of code if specified condition is true.

In C#, we write an if statement using the following syntax:
```c#
string color = "blue";

if (color == "blue")
{
  // this code block will execute only if the value of color is 
  // equivalent to "blue"
  Console.WriteLine("color is blue");
}
```
In this example, our if conditional statement checks to see if the value of the variable color is equivalent to the string "blue". Since it is, it will execute the code in the code block and print the string "color is blue" to the console. If color equals another value or was null, the program skips over the block and moves on to the next instruction.

When writing an if statement, make sure to pay attention to:

Parentheses: we place the boolean expression that the if statement is evaluating in parentheses ().
Braces: after the boolean expression, we write a set of braces {}. Write the code that will execute if the boolean expression evaluates to true inside these braces.
Indentation: while whitespace won’t impact our program, it is convention to indent the code inside the braces by two spaces.

## Instructions

You take your laundry to the laundromat once you have exactly three pairs of socks or less left. Write an if statement to check whether or not it’s time to take your laundry in. Leave the code block empty for now.

If the condition is true, have it print Time to do laundry! to the console.

Now try changing the value of socks to 6. What happens this time?

## My Code
```c#
using System;

namespace IfStatement
{
  class Program
  {
    static void Main(string[] args)
    {
      int socks = 6 ;

      if (socks <= 3) {
        
        Console.WriteLine("Time to do laundry!")
          
      };

    }
  }
}

```
