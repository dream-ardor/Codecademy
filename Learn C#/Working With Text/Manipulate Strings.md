## Manipulate Strings

There are also built-in .NET methods that we can use to manipulate text data. Using these methods on a string doesn’t change the string itself, but creates an entirely new one.

### ToUpper, ToLower

We can quickly change the case of our strings using the methods .ToUpper() and .ToLower(). These methods are useful if we want to make our text look like an e.e. cumming’s poem or make it appear like we forgot to turn off our caps lock key.
```c#
string shouting = "I'm not shouting, you're shouting".ToUpper();
Console.WriteLine(shouting);
// prints I'M NOT SHOUTING, YOU'RE SHOUTING.
```
## Instructions

You’re writing a movie script but are having trouble following the style guide. You need to transform this sentence so that the first two words (Close on) are in all caps and the rest is lower case.

Close on a portrait of the HANDSOME PRINCE -- as the BEAST'S giant paw slashes it.
Your assistant already started on this program and separated out the necessary strings and saved them in the variables cameraDirections and sceneDescription. You need to finish the program.

First, make all of the letters in cameraDirections uppercase and re-save them to the variable cameraDirections.

Now make all of the letters in sceneDescription lowercase and resave them to the variable sceneDescription. Print your results to the console.

## My Code
```c#
using System;

namespace MovieScript
{
  class Program
  {
    static void Main(string[] args)
    {
      // Script line
      string script = "Close on a portrait of the HANDSOME PRINCE -- as the BEAST'S giant paw slashes it.";

      // Get camera directions
      int charPosition = script.IndexOf("Close");
      int length = "Close on".Length;
      string cameraDirections = script.Substring(charPosition, length);

      // Get scene description
      charPosition = script.IndexOf("a portrait");
      string sceneDescription = script.Substring(charPosition);

      // Make camera directions uppercase

 cameraDirections = cameraDirections.ToUpper();
      // Make scene description lowercase
sceneDescription = sceneDescription.ToLower();
         // Print results
  Console.WriteLine(cameraDirections);
  Console.WriteLine(sceneDescription);
    }
  }
}
```
