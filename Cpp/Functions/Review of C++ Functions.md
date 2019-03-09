## FUNCTIONS

### Review of C++ Functions

Wow! Check out all you've learned about C++ functions:

* A function is a named group of statements that do something together.
* Functions allow you to create more flexible, modular, and DRY code.
* C++ has many built-in functions that you can use.
* Functions are called like function_name();
* A function has a declaration with a return type and possible parameters.
* A function has a definition (or body) with a group of statements and a possible return value.
* void functions do not have return values.
* Functions with a return value have return statements.
* Parameters are variables used as placeholders for function input values.
* Arguments are a function's actual input values.
* Variables defined inside a function have local scope.
* Variables defined with global scope are accessible everywhere in a program.
* Functions are generally stored in a header file.
* You now know enough C++ to create some pretty cool projects on your own. But, as you'll see, there are often many ways to improve your code.

### Instructions

Try using functions to rewrite (or refactor) that IT conversation program we showed you. Maybe move the function to the header file provided to clean up your code even more and make everything even more modular.

You can also use this space to play around with building your own functions. Have fun!

## Code
```c++
#include <iostream>

int main() {
  
  // Conduct IT support
  std::string on_off_attempt;
  std::cout << "Hello. IT.\n";
  std::cout << "Have you tried turning it off and on again? y/n\n";
  std::cin >> on_off_attempt;
  
  // Check in with Jenn
  std::cout << "Oh hi Jen!\n";
  
  // Conduct IT support again...
  std::cout << "Hello. IT.\n";
  std::cout << "Have you tried turning it off and on again? y/n\n";
  std::cin >> on_off_attempt;

  // Check in with Roy
  std::cout << "You stole the stress machine? But that's stealing!\n";
  
  // Conduct IT support yet again...zzzz...
  std::cout << "Hello. IT.\n";
  std::cout << "Have you tried turning it off and on again? y/n\n";
  std::cin >> on_off_attempt;
  
}
```
