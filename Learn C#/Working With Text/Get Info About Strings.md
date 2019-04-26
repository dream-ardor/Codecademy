## Get Info About Strings

In addition to containing the value of a piece of text, strings also contain information about themselves. It can be useful to know these properties when working with strings. There are several built-in .NET methods that we can use to get more information about strings.

### Length

Since strings are composed of a set of characters, we can find out how many characters exist in a string with the .Length method. A common example is if we’re building a form and need to make sure a user submission doesn’t exceed a certain character length.
```c#
string userTweet = Console.ReadLine();

userTweet.Length; // returns the length of the password
```
We append the .Length property to a string that we have, such as a user’s tweet.

### IndexOf

We can also find the position of a specific character or substring using .IndexOf(). This method is useful for searching to see if something exists in a string.

If it does exist within a string, the method will return the position of the search term in the larger string. Each character in a string has a unique position, like an address. Positions starts at 0 and increment by 1.
```c#
string word = "radio";

word.IndexOf("a"); // returns 1
```
Since positioning starts at 0, the second thing in the string will return a 1. If it doesn’t exist in the string the method will return a -1. If we pass it an empty string, it will return 0. If it occurs more than once, it will return the first instance.

## Instructions

You’ve been asked to build a program that verifies some information about a piece of data.

First, check the length of password and save the result to the variable passwordLength.

Next, let’s see if this password contains any special characters, like an exclamation point (!). Save the result to the variable passwordCheck. Run the program to see the results printed to the console.

## My Code
```c#
using System;

namespace PasswordCheck
{
  class Program
  {
    static void Main(string[] args)
    {
      // Create password
      string password = "a92301j2add";

      // Get password length
int passwordLength = password.Length;
    
      // Check if password uses symbol
int passwordCheck = password.IndexOf("!");
      // Print results
      Console.WriteLine($"The user password is {password}. It's length is {passwordLength} and it receives a {passwordCheck} check.");

    }
  }
}
```
