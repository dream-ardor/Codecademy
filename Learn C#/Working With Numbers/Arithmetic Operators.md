## Arithmetic Operators
So what can we do with numerical data? A first step is to write expressions using arithmetic operators.

Arithmetic operators include:
```
addition +
subtraction -
multiplication *
division /
```
We can use these symbols to perform operations on numbers and create new values.
```c#
int answer = 4 + 19;
Console.Write(answer);

// prints 23
```
When using operators, it’s important to pay attention to data types. If we use two integers, it will return an integer every time. However, if we combine an integer with a double, the answer will be a double. Let’s look at the following example:
```c#
Console.WriteLine(5 / 3);
Console.WriteLine(5 / 3.0);

// prints 1
// prints 1.66667
```
The first operation that we log uses two ints. While 3 doesn’t go into 5 evenly, we are still left with an int whole number. In the second operation, we use an int and a double, so the final result is a double.

C# follows the order of operations. If we do 1 + 2 * 3, should the answer be 9 or 7? C# follows a set of rules to determine which operations to perform first (the answer is 7). It’s good practice to use parentheses to explicitly tell C# how to calculate these expressions.

Notice in the following example, even if the addition symbol appears like it should come first, the multiplication operation will happen first.
```c#
int answer = 8 + (9 * 3);
Console.Write(answer);

// prints 35
```

## Instructions

Did you know that your age would be different on another planet? Different planets orbit the sun at different rates, so 1 year on earth can be much shorter or much longer on another planet, depending on their position in the solar system.

Let’s start by saving your age on Earth in a variable named userAge.

We’re going to write an equation that calculates your age on Jupiter.

To calculate a person’s age on another planet, we need to know how long it takes each planet to orbit the Sun (relative to a year on Earth):

Jupiter takes 11.86 years

Create a variable named jupiterYears and save the amount of years it takes to orbit as their value.

Next we’ll write the calculations. The formula for calculating an age on another planet is: divide the user age in Earth years by the length of the other planet’s year (in Earth years) to get your age in that planet’s years.

Calculate your age in Jupiter years and save it to the variable jupiterAge.

If we were to fly to Jupiter, it could take as long as 2,242 (Earth) days or about 6.142466 years!

Save the value 6.142466 to a variable named journeyToJupiter.

When you reach Jupiter:

What would be your age in Earth years? Save your answer to newEarthAge.
What would be your age in Jupiter years? Save your answer to newJupiterAge.

Log the ages on the different planets to the console so you can see your age on each planet currently, and after your journey to Jupiter.

## My Code
```c#
using System;

namespace PlanetCalculations
{
  class Program
  {
    static void Main(string[] args)
    {  
      // Your Age
int userAge = 39;
      

      // Length of years on Jupiter (in Earth years)
double jupiterYears = 11.86;
      
    
      // Age on Jupiter
double jupiterAge = userAge / jupiterYears;

      // Time to Jupiter

double journeyToJupiter = 6.142466;
      // New Age on Earth
double newEarthAge = userAge + journeyToJupiter;

      // New Age on Jupiter
double newJupiterAge = newEarthAge/jupiterYears;
      // Log calculations to console
      Console.WriteLine(userAge);
      Console.WriteLine(newEarthAge);
      Console.WriteLine(jupiterAge);
      Console.WriteLine(newJupiterAge);
    }
  }
}
```
