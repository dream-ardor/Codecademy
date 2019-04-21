## Introduction to Working with Numbers

No matter what you want to make in C#, you’ll need numbers!

Art: what are the dimensions of your canvas?
Games: how fast can your player move?
Business: how much does your product cost?

In this lesson, we’ll look at a few of the most commonly used numerical data types in C#. By the end of this lesson, you will be able to manipulate numerical data and write programs that perform calculations using arithmetic operators and built-in methods.

## Instructions

Take a look at the C# program in the code editor window. What do you think it will do? Run the code and see if you’re correct.

```c#
using System;

namespace BusinessSolution
{
  class Program
  {
    static void Main(string[] args)
    {
      // Calculating Net Income 
      double revenue = 853023.45;
      double expenses = 438374.11;
      double netIncome = revenue - expenses;

      Console.WriteLine(netIncome);

      // Calculating a Break-Even Point
      double fixedCosts = 912849.30;
      double salesPrice = 29.99;
      double variableCostPerUnit = 17.65;

      double breakEvenVolume = fixedCosts / (salesPrice - variableCostPerUnit);
      Console.WriteLine(breakEvenVolume);
    }
  }
}

```
