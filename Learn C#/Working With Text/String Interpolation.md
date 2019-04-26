## String Interpolation

While string concatenation is easy to read, it can get annoying to write. Another option is string interpolation. String interpolation was introduced in C# 6 and it enables us to insert our variable values and expressions in the middle of a string, without having to worry about spaces and punctuation.
```c#
string yourFaveMusician = "David Bowie";
string myFaveMusician = "Solange";

Console.WriteLine($"Your favorite musician is {yourFaveMusician} and mine is {myFaveMusician}.")
```
Notice how we just have one string, which we append with the dollar sign symbol $. Make sure there isn’t a space in between the $ and the starting quotation mark ". Whenever we need to insert a variable, we surround it with braces {}.For more on string interpolation, check out Microsoft’s documentation.

In older documentation, you may come across a slightly similar syntax. This style is known as string formatting or composite formatting. Since the introduction of string interpolation, it is rarely used. But in case you come across it, check out Microsoft’s documentation.

## Instructions

Let’s revisit our story, but use string interpolation. This time we’ve provided you with the variables.

Using the provided beginning, middle, and end variables, interpolate the story variable.

Print the story to the console. Reflect on using string concatenation and string interpolation to achieve the same outcome. Which one did you prefer?

## My Code
```c#
using System;

namespace StoryTime
{
  class Program
  {
    static void Main(string[] args)
    {
      // Declare the variables
      string beginning = "Once upon a time,";
      string middle = "The kid climbed a tree";
      string end = "Everyone lived happily ever after.";

      // Interpolate the string and the variables
string story = $"{beginning} {middle} {end}";
      // Print the story to the console 
      Console.WriteLine(story);

    }
  }
}
```
