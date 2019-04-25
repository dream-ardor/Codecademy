## Introduction to Working with Text

Working with text is a fundamental part of writing programs. Whether it’s to provide instructions to a user, gathering data like a name or address, or writing a new form of poetry, text enables us to bring human language into computational form.

In this lesson, we’ll look at the two commonly used text data types in C#: char and string. By the end of this lesson, you will be able to manipulate textual data and write programs that take in user inputs and output customizable messages using variables, operators, and built-in methods.

## Instructions

Take a look at the program on the right. What do you think the outcome will be? This program uses many of the techniques that you’ll learn in this lesson!

```c#
using System;

namespace MadTeaParty
{
  class Program
  {
    static void Main(string[] args)
    {
      string drink = "wine";
      string madTeaParty = $"\"Have some {drink},\" the March Hare said in an encouraging tone. \nAlice looked all round the table, but there was nothing on it but tea.\n\"I don't see any {drink},\" she remarked.\n\"There isn't any,\" said the March Hare.";

      int storyLength = madTeaParty.Length;
      string toFind = "March Hare";

      string findLowerCase = toFind.ToLower(); 
      int findMarchHare = madTeaParty.IndexOf(toFind);

      Console.WriteLine(madTeaParty.Substring(findMarchHare));
      Console.WriteLine($"This scene is {storyLength} long.\n");
      Console.WriteLine($"The term we're looking for is {toFind} and is located at index {findMarchHare}.");

    }
  }
}

```
