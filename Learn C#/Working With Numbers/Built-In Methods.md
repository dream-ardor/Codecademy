## Built-In Methods

So how do we do more advanced mathematical operations? For example, how would we perform a square root on a number if the program doesn’t recognize a square root symbol?

There are several built-in methods that we can use to manipulate numerical data and perform more complex mathematical calculations. Here are a few:

* Math.Abs()—will find the absolute value of a number. Example: Math.Abs(-5) returns 5.
* Math.Sqrt()—will find the square root of a number. Example: Math.Sqrt(16) returns 4.
* Math.Floor()—will round the given double or decimal down to the nearest whole number. Example: Math.Floor(8.65) returns 8.
* Math.Min()—returns the smaller of two numbers. Example: Math.Min(39, 12) returns 12.

## Instructions

In this exercise, we’re going to use built-in methods to determine which number is smaller between the square roots of two different numbers.

First, find the square root of numberOne and round the answer down so it doesn’t have a decimal. Save this value to a new double variable numberOneSqrt.

Do the same process to variable numberTwo and save this value to a new double variable numberTwoSqrt.

Inside of a Console.WriteLine() statement, use a built-in method that returns the smallest of two numbers, using the values numberOneSqrt and numberTwoSqrt.

Which value gets printed to the console?

Did NaN get printed to the console? NaN stands for “Not a Number” in C#. So what happened?

The built-in method Math.Sqrt() can only take a positive number as a value, but the value of numberTwo is negative. But we can fix it. The method Math.Abs() will find the absolute value of a number. A good reminder that when we use built-in methods, to check the documentation so we know how to use them!

Inside of the Math.Sqrt() method, add the Math.Abs() method, so it takes the variable numberTwo as a value. Re-run the code and see what gets printed to the console this time!

## My Code
```c#
using System;

namespace LowestNumber
{
  class Program
  {
    static void Main(string[] args)
    {
      // Starting variables 
      int numberOne = 12932;
      int numberTwo = -2828472;

      // Use built-in methods and save to variable 
 double numberOneSqrt = Math.Floor(Math.Sqrt(numberOne)); 
      

      // Use built-in methods and save to variable 
double numberTwoSqrt =
  Math.Floor(Math.Sqrt(Math.Abs(numberTwo)));
      

      // Print the lowest number
Console.WriteLine(Math.Min(numberOneSqrt,numberTwoSqrt));
      
    }
  }
}
```
