## Exponentiation

PHP give us an operator for raising a number to the power of another number: the exponentiation operator (**).

For example, we can square a number by raising it to the power of 2:
```php
echo 4 ** 2; // Prints: 16
```
We can also use this operator on floats and negative numbers:
```php
echo 2.89 ** 3.2;  // Prints: 29.845104015297
echo 10 ** -1; // Prints: 0.1
```
For PHP to interpret this operator correctly it can’t have any spaces between the two * characters:
```php
echo 2 * * 3; // Will result in an error
```
Let’s do some more math!

### Instructions

Use echo and the exponent operator to print the value of 8 squared to the terminal.

## My Code
```php
<?php
// Write your code below:
  
echo 8 ** 2;

```
