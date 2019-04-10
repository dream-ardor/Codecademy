## Creating Variables

Let’s look at an example of creating a variable:
```php
$my_name = "Aisle Nevertell";
```
In the code above, we’re actually doing two things with a single statement: we’re declaring a new variable by giving it the name my_name. We’re also assigning it the value "Aisle Nevertell". The variable $my_name now holds the value "Aisle Nevertell".

To declare a variable we use the dollar sign character ($) followed by our chosen variable name. The dollar sign is known as a sigil; it’s a character that allows the computer to see quickly that something is a variable.

To assign it a value we use another operator: the assignment operator (=) followed by the value we’re assigning to the variable.

Though it can occasionally be useful to separate these actions, we’ll most often be declaring and assigning variables at the same time.

In PHP, variables names can contain numbers, letters, and underscores (_), but they have to start with either a letter or an underscore. Variable names are case sensitive, meaning that PHP will treat the variables $my_example and $My_example as two different variables.

One common convention when naming PHP variables is to use an underscore between words on variable names with more than one word in their name. This is known as snake case:
```php
$mood = ":)";
$favorite_food = "Red curry with eggplant";
```
Let’s create some variables!

### Instructions

Create a variable and assign to it a string value. You can give the variable any valid name you’d like and assign a string containing anything you want. End the statement with a semicolon.

Declare a variable $biography and assign to it a string that starts with a new line character and contains a sentence or two about you.

Create a variable $favorite_food and assign to it the string "\n", "tur", "duck", and "en" concatenated together.

## My Code
```php
<?php
// Write your code below:  
$myPowerLevel = "huge";
$biography = "\n Beautiful women love me and lust after me";
$favorite_food = "\n" . "tur" . "duck" . "en";

```
