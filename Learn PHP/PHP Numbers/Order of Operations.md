## Order of Operations

We can chain multiple operations together to get a single result:
```php
echo 2 + 3 + 4 + 5 - 1.1; // Prints: 12.9
echo 2 * 9 / 6; // Prints: 3
```
You might have learned about operations having an order of precedence in a math class. This means that operations in a chain aren’t simply performed from left to right; rather each operator is given a special rank.

Operations will be evaluated in the following order:

* Any operation wrapped in parenthesis (())
* Exponents (**)
* Multiplication (*) and division (/)
* Addition (+) and subtraction (-).

The acronym PEMDAS can be helpful for remembering the order of precedence for these arithmetic operations.
```php
echo 1 + 3 * 9; // Prints: 28
```
In the example above, 3 * 9 (27) is calculated first and then is added to 1 to yield a final result of 28. We can change what this expression returns by using parenthesis:
```php
echo (1 + 3) * 9; // Prints: 36
```
Here, 1 + 3 (4) is calculated first and then that value is multiplied by 9 to which returns 36.

Let’s practice writing some chained operations!

### Instructions

Heya! Can you help me out. Use echo to print the answer to the terminal.

I’m trying to figure out how much money I should have. At the start of the day I had $94.

* I spent $4.25 on coffee
* A friend gave me $7 that he owed me
* I went out for a meal. The bill was $23.50, but I also gave a 20% tip.
* Some friends and I found $20 on the ground and split it four ways

I think that’s everything.

Use a single chained operation to get your result!

## My Code
```php
<?php
// Write your code below:

echo 94 - 4.25 + 7 - (23.50 * 1.2) + 20 / 4;

```
