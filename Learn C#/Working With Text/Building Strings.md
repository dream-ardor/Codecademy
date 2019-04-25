## Building Strings

A string is a group of characters surrounded by quotation marks, like "https://codecademy.com" or "To be or not to be." A string is just a collection of a smaller data type, char, which is a single character like “a” or “?”.

To define a variable as a string, you write the data type, then the variable name. Then set it equal to the value, which is inside of quotation marks :
```c#
string variableName = "puppy";
```
The variable is named variableName, it’s of type string, and it’s value is "puppy".

### Escape Character Sequences

What happens when you need to include quotes in a string? You can use an escape sequence. An escape sequence places a backslash (\) before the inner quotation marks, so the program doesn’t read them accidentally as the end of sequence.
```c#
string withoutSlash = "Ifemelu said, "Hello!"";

string withSlash = "Ifemelu said, \"Hello!\"";
```
We can use escape character sequences to create a newline. That means that when we print the string to the console, it will print that line below the rest. If printed on its own, it will create an empty line. To create a newline, use the character combination \n.
```c#
string newLine = "Ifemelu walked \n to the park.";
```
For more on escape sequences, check out Microsoft’s Documentation.

## Instructions

Create a string variable named firstSentence and save the following string to it:

It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.

Create a second string variable named firstSpeech and save the following string to it:

"My dear Mr. Bennet," said his lady to him one day, "have you heard that Netherfield Park is let at last?"
Make sure to use escape characters when necessary.

Using Console.WriteLine(), print each variable to the console. In between them, print a newline to the console.

## My Code
```c#
using System;

namespace PrideAndPrejudice
{
  class Program
  {
    static void Main(string[] args)
    {
      // First string variable
      string firstSentence = "It is a truth universally acknowledged, that a single man in possession of a good fortune, must be in want of a wife.";
      // Second string variable
      string firstSpeech = "\"My dear Mr. Bennet,\" said his lady to him one day, \"have you heard that Netherfield Park is let at last?\"";

      // Print variable and newline
      Console.WriteLine(firstSentence);
      Console.WriteLine("\n");
      Console.WriteLine(firstSpeech);
    }
  }
}
```
