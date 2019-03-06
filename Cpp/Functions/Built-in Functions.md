## FUNCTIONS

### Built-in Functions

C++ comes chock-full of functions that are already created as part of the standard C++ library. But how do you access this hidden hoard of helpful functions? You gain access to various functions by including headers like <cmath> or <string>.

In fact, you may already have used a couple functions without even knowing it! With the following header:
```c++
#include <cmath>
```
You gain the power to use sqrt() to find the square root of a number.

Similarly, using <cstdlib> (which is included with your <iostream> header) you could call rand() to produce a random integer.

Wait, "call" rand()? Call it what?

Calling a function is how we get a function to take action. To call the most basic function, you just need the function name followed by a pair of parentheses. For example:
```c++
std::cout << sqrt(9) << "\n";
// This would output 3
```
### Instructions

Inside of main(), call rand() with the modulo operator to generate a random number between 0 and your favorite number (e.g., rand() % 28 would give you a random number between 0 and 28).

Assign the resulting value to a new int variable called the_amazing_random_number.

Print the_amazing_random_number to the terminal.

## My Code
```c++
#include <iostream>

int main() {
  
  // This seeds the random number generator:
  srand (time(NULL));
  
  // Use rand() below to initialize the_amazing_random_number
  int the_amazing_random_number = rand() % 69;
  std::cout << the_amazing_random_number;
  
}
```
