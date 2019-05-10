## Documentation

In order to understand built-in functions we’ve never used before, we’ll want to get comfortable understanding how they are represented in the documentation. Documentation typically includes:

* The name of the function.
* The versions of the PHP language the function is available in.
* An overview of how the function works.
* Additional details on the parameters and return value.
* Examples of the function in use.
* User comments further explaining features of the function.

The description section can be confusing, so we’ll break that down.

Here’s the description for the abs() function:
```php
abs ( mixed $number ) : number
```
Here we see the function name followed by parentheses. The parentheses contain information about the function’s parameter(s)—first the parameter’s type followed by its name. The parameter for abs() has the type mixed because there are multiple data types the function will accept (an integer or a float). The parameter for abs() is named $number. After the parentheses is a colon (:) followed by number; this is the data type the function will return.

A function that prints something but doesn’t return a value will have :void instead of a return type. Similarly, a function that doesn’t accept parameters will have void within its parentheses.

Let’s look at a more complicated example. Here’s the description for the substr_count() function:
```php
substr_count ( string $haystack , string $needle [, int $offset = 0 [, int $length ]] ) : int
```
Earlier in this lesson, we invoked substr_count() with only the two string parameters ($haystack and $needle). But functions can have optional parameters. This means they’ll work with or without them. These parameters are wrapped in square brackets ([ ]) in the function’s description. An optional parameter may have a default value, this is the value that will be used if no argument is passed into the function. The default value is indicated with an equal sign (=).

The substr_count() function accepts two additional integer arguments—$offset and $length. $offset has a default value of 0. Take a look at the documentation and see if you can figure out what they do.

Let’s practice reading some function descriptions!

## Instructions

Here’s the description for the str_pad() built-in function:
```php
str_pad ( string $input , int $pad_length [, string $pad_string = " " [, int $pad_type = STR_PAD_RIGHT ]] ) : string
```
In the code editor, we’ve provided four variables: $a, $b, $c, and $d. Your task is to invoke str_pad() with these four variables as its arguments so that it returns the string: *~**~**~*You did it!*~**~**~*. You’ll need to figure out which order to pass them in.

Use echo to print the result of invoking the function.

This task is designed to be a little challenging. Check out the documentation for more information, and take a look at the hint for more guidance.

Note: One of the arguments (and its corresponding variable) is a PHP type we haven’t taught yet: pre-defined constants. You can solve this challenge without understanding them deeply. Predefined constants are similar to variables—they’re names which hold values. Unlike variables, predefined constants are defined by the language, not by us, and they’re constant, they can’t change value.

## Solution
```php
<?php
namespace Codecademy;

$a = 29;
$b = "You did it!";
$c = STR_PAD_BOTH;
$d = "*~*";

// Write your code below:
echo str_pad($b,$a,$d,$c);
```
