## Comments

Ironically, an essential tool in programming is the ability to tell a computer to ignore a part of a program. Text written in a program but not run by the computer is called a comment. In C#, anything after a // or between /* and */ is a comment. In spoken word we call these symbols “forward slashes” and “asterisks”.

Comments can:

Provide context for why something is written the way it is:
```c#
/* This variable will be used to count the number of times anyone tweets the word persnickety */
int persnicketyCount = 0;
Help other people reading the code understand it faster:

/* Calculates tomorrow's rain likelihood as a number between 0 and 100 */
ComplicatedRainCalculationForTomorrow();
Ignore a line of code and see how a program will run without it:

// string usefulValue = OldSloppyCode();
string usefulValue = NewCleanCode();
```
Developers tend to use // for short, one-line comments and /* */ for anything longer, but the choice is up to you!

## Instructions

Add a comment to the code right above the first Console.WriteLine().

The comment should explain what this program does.

## My Code
```c#
using System;

namespace GettingInput
{
  class Program
  {
    static void Main()
    {
      //asking for your age as input and displays the answer
      Console.WriteLine("How old are you?");
      string input = Console.ReadLine();
      Console.WriteLine($"You are {input} years old!");
    }
  }
}

```
