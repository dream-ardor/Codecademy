## Using Documentation

We introduced you to a few common built-in methods, but there are many more out there! Now’s a good time to practice your documentation search skills. Take a moment to look up the following built-in methods to understand their usage:
```c#
Math.Pow()
Math.Max()
Math.Ceiling()
```
(If you’re having trouble locating what you need, we recommend the Microsoft .NET API documentation).

## Instructions

In this exercise, you’ll need to use the documentation linked above.

Inside of the first Console.WriteLine() command, raise numberOne to the numberTwo power.

Inside of the second Console.WriteLine() command, round numberOne up.

Inside of the third Console.WriteLine() command, find the larger number between numberOne and numberTwo.

## My Code
```c#
using System;

namespace DocumentationHunt
{
  class Program
  {
    static void Main(string[] args)
    {

      double numberOne = 6.5;
      double numberTwo = 4;

      // Raise numberOne to the numberTwo power
      Console.WriteLine(Math.Pow(numberOne,numberTwo));
      // Round numberOne up
      Console.WriteLine(Math.Ceiling(numberOne));

      // Find the larger number between numberOne and numberTwo
      Console.WriteLine(Math.Max(numberOne,numberTwo));

    }
  }
}
```
