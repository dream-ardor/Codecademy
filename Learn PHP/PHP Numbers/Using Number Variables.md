## Using Number Variables

We can use number operators on variables that hold number values:
```php
$tadpole_age = 7;
$lily_age = 6; 
$age_difference = $tadpole_age - $lily_age;
echo $age_difference; // Prints 1
```
Let’s look at another example of performing operations with number variables:
```php
$favorite_num = 22;
echo $favorite_num + 1; // Prints 23
echo $favorite_num; //Prints 22
```
In the code above, we created the variable $favorite_num then we used echo to print that value plus 1. Note that we didn’t reassign the value of the $favorite_num variable, so it still had the value 22 when we printed it on the last line.

We reassign number variables using the assignment operator:
```php
$age = 82;
echo $age; // Prints: 82

$age = $age + 2;
echo $age; // Prints: 84
```
Let’s do some addition and subtraction with variables!

### Instructions

Can you help? I’m trying to figure out how much more I spent last month than this month. Last month I spent 1187.23 and this month I spent 1089.98. Create the variables $last_month and $this_month and assign them the corresponding numeric values.

Use echo to print the difference between last month’s spending and this month’s.

## My Code
```php
<?php
// Write your code below:
  
  $last_month = 1187.23;
  $this_month = 1089.98;

echo $last_month - $this_month;

```
