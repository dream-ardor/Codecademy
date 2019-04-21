## Numerical Data Types

In C#, there are several ways of representing numerical data. Your usage of each will depend on your application. When choosing a data type, think about the following questions:

Do I need a whole number or do I need something that will represent a fraction, or a decimal? If I want to use a decimal, how precise do I need to be? Depending on your application, whether it’s a hobby project or building a B2B financial services software, you’ll need a different data type. Is performance a factor? Most times, choosing a data type that takes up less memory will result in faster applications.

Let’s look at two data types that we can use to represent different numerical values:

### Int
An int is a whole integer value, like 4, 100, or 2349. They’re a good way to count units of things. For example, if we wanted to track the number of coin flips a user makes, we’d use an int. It doesn’t make sense to have 0.5 coin flips!

To define a variable with the type int, you would write it as follows:
```c#
int variableName = 7;
```

### Double and Decimal
If we need to use a decimal value, we have a few options: float, double, and decimal. These values are useful for anything that requires more precision than a whole number, like measuring the precise location of an object in 3D space.

A double is usually the best choice of the three because it is more precise than a float, but faster to process than a decimal. However, make sure to use a decimal for financial applications, since it is the most precise.

To define a variable with the type double, you would write it as follows:
```c#
double variableName = 39.76876;
```
To define a variable with the type decimal, you would write it as follows:
```c#
decimal variableName = 489872.76m;
```
Don’t forget the m character after the number! This character tells C# that we’re defining a decimal and not a double.

### Instructions

Several large pizza chains employee C# developers. Let’s imagine that you work for the chain, Giant Brutus. Your boss gives you some data and wants you to enter it into a C# program.

The first value they give you is the number of pizza shops they own, which is 4332. Save this number to a variable named pizzaShops. Which data type should you use for the variable?

The next value is the number of employees, which is 86,928. Save this number to the variable totalEmployees.

The total revenue for a single Big Brutus franchise store is 39,0819.28. Save this number to the variable revenue.

Print the three variables to the console.

## My Code
```c#
using System;

namespace Numbers
{
  class Program
  {
    static void Main(string[] args)
    {
      // Number of pizza shops
   int pizzaShops = 4332;
      
      // Number of employees
   int totalEmployees = 86928;

      // Revenue
decimal revenue = 390819.28;

      // Log the values to the console:
Console.WriteLine(pizzaShops);
      Console.WriteLine(totalEmployees);
      Console.WriteLine(revenue);
   	}
  }
}
```

