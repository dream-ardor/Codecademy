## Working with Variables

PHP includes useful built-in functions for getting information about variables. The gettype() function takes a variable as its argument and returns a string value representing the data type of the argument.
```php
$name = "Aisle Nevertell";
$age = 1000000;

echo gettype($name); // Prints: string

echo gettype($age); // Prints: integer
```
Notice that we didn’t write a definition for the gettype() function ourselves—it’s built into PHP. Since the function is included within the language itself, we can just call it anywhere within our PHP code.

Let’s take a look at another built-in function! The var_dump() function also takes a variable argument. It prints details about the argument it receives.
```php
var_dump($name); // Prints: string(15) "Aisle Nevertell"

var_dump($age); // Prints: int(1000000)
```
In the code above, we first used var_dump() to print information about the variable $name. string(15)—the variable’s type and length—were printed followed by the value held by the variable.

Next, we used var_dump() to print information about the variable $age. Here, the integer is printed within the parentheses.

As we learn more data types—especially increasingly complex data types—we’ll see how useful these two functions can be. For now, let’s practice using them with the types of data we know!

## Instructions

Using echo and the gettype() function, print the data types of the $first and $second variables.

Let’s compare that to what var_dump() outputs. Use var_dump() to display information about the $first and $second variable.

## My Code
```php
<?php
namespace Codecademy;

$first = "Welcome to the magical world of built-in functions.";
  
$second = 82137012983; 

//Write your code below:
echo gettype($first);
echo gettype($second);
echo var_dump($first);
echo var_dump($second);

```
