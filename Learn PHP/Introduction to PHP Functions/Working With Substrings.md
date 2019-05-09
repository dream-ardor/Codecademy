## Working with Substrings

A substring is a portion of a string. For example, "hello" is a substring of the string "Oh hello, how are you?" and "el" is a substring of the string "hello". Manipulating strings is very common in programming, and working with substrings is often necessary.

The substr_count() function returns the number of instances of a substring within a string. It takes two arguments, the string to search through—sometimes called the haystack— and the string to search for—sometimes called the needle.
```php
$story = "I was like, \"Dude, like just tell me what you like think because like everyone else is like being totally honest, and like I just want to know what you like think.\" So like I don't know...";

echo substr_count($story, "like"); // Prints: 8
```
In the code above, we invoked the substr_count() function, passing in $story as the haystack and "like" as the needle. We used echo to print the returned result—8, which is the number of times the substring "like" appears in the $story string.

Let’s practice!

## Instructions

Use echo and the substr_count() function to print the number of times the word “really” appears in $essay_one.

Use echo and the substr_count() function to print the number of times the word “obvious” appears in $essay_two.

Notice that substr_count() is not concerned with which characters come before or after the string it’s searching for—it will count both “obvious” and “obviously”.

## My Code
```php
<?php
namespace Codecademy;

$essay_one = "I really enjoyed the book. I thought the characters were really interesting. The plot of the novel was really engaging. I really felt the characters' emotions. They were really well-written. I really wish the ending had been different though.";
  
$essay_two = "Obviously this is a really good book. You obviously would not have made us read it if it wasn't. I felt like the ending was too obvious though. It was so obvious who did it right away. I think the thing with the light was obviously a metaphor for life. It would have been better if the characters were less obvious about their secrets.";  

// Write your code below:
echo substr_count($essay_one, "really");
echo substr_count($essay_two,"obvious");
```
