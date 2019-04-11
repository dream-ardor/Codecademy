## Assign by Reference

When we create a variable assigned to another variable, the computer finds a new space in memory which it associates with the left operand, and it stores a copy of the right operand’s value there.

This new variable holds a copy of the value held by the original variable, but it’s an independent entity; changes made to either variable won’t affect the other:
```php
$first_player_rank = "Beginner"; 
$second_player_rank = $first_player_rank; 
echo $second_player_rank; // Prints: Beginner

$first_player_rank = "Intermediate"; // Reassign the value of $first_player_rank
echo $second_player_rank; // Still Prints: Beginner
```
We can also create an alias, or nickname, for a variable. Instead of a copy of the original variable’s value, we create a new name which points to the same spot in memory.

We use a different operator for this—the reference assignment operator (=&).

When we assign by reference we’re saying that the variable on the left of the operator should point, or refer, to the exact same data as the variable on the right. With assignment by reference, changes made to one variable will affect the other:
```php
$first_player_rank = "Beginner";
$second_player_rank =& $first_player_rank; 
echo $second_player_rank; // Prints: Beginner

$first_player_rank = "Intermediate"; // Reassign the value of $first_player_rank
echo $second_player_rank; // Prints: Intermediate
```
Ok, let’s get some practice!

## Instructions

You’ve inherited some code from another developer. You can’t change their code, but you need to add some additional functionality. Instead of using the $very_bad_unclear_name variable as is in your part of the code. Declare a new variable, $order, as a reference to the $very_bad_unclear_name variable.

Use the concatenation assignment operator to append more things to $order.

Awesome! Notice how when we echo the $very_bad_unclear_name variable at the end of the programs, the changes you made are reflected in the output!

## My Code
```php
<?php
/* Imagine a lot of code here */  
  $very_bad_unclear_name = "15 chicken wings";

// Write your code here:
$order =& $very_bad_unclear_name;

$order .= ", 2 sodas";
$order .= ", 2 fries";
$order .= ", bbq sauce";

    
  // Don't change the line below
  echo "\nYour order is: $very_bad_unclear_name.";

```
