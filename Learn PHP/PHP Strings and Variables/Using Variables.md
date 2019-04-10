## Using Variables

Once we’ve declared a variable and assigned a value to it, we can use it as many times as we want. We refer to a variable by using the dollar sign followed by the variable’s name.
```php
$favorite_food = "Red curry with eggplant, green beans, and peanuts";
echo $favorite_food; 
// Prints: Red curry with eggplant, green beans, and peanuts
```
Except during assignment, whenever the computer sees a variable in your code, it replaces the variable with the value assigned to that variable.
```php
$dog_name = "Tadpole";
echo $dog_name; 
// Prints: Tadpole
```
Since the computer treats a variable just as if it were the value it holds, this means we can do operations on variables just as we would with any value of that type.
```php
$dog_name = "Tadpole";
echo "My dog is named " . $dog_name; 
// Prints: My dog is named Tadpole
```
In the code above, we concatenated the string "My dog is named " to the value held by the $dog_name variable ("Tadpole"). Let’s look at another example that uses multiple variables:
```php
$dog_name = "Tadpole";
$favorite_food = "salmon";
$color = "brown";

echo "I have a " . $color . " dog named " . $dog_name . " and her favorite food is " . $favorite_food . ".";
// Prints: I have a brown dog named Tadpole and her favorite food is salmon.
```
Let’s use some variables!

### Instructions

You’re going to create a couple variables. The variable, $name, should be assigned your name as a string. The second,$language, should be assigned a string value representing a language you’re learning.

Use echo to print any string you’d like with the $name variable concatenated to it.

Use echo to print a string starting with a newline (\n) with $language variable concatenated to it.

## My Code
```php
<?php
// Write your code below:
  
$name = "Dan";
$language = "JavaScript";

echo "I love " . $name;
echo "\nI like to study " . $language;
```
