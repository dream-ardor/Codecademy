## FUNCTIONS

### Getting a Header Yourself

Putting a single function definition above main() is all well and good, but what if you have a whole bunch of functions?

With a few functions, you can declare the function above main() and then define the function below main(). But ultimately you probably need to move your functions over to another file: main.hpp, known as the header file.

The header can store more than just functions — it can also store all of your library #include statements, like <iostream> (which you will need for your functions to run)! But files, like functions, have scope. How do you bring everything from one file into scope for another file? By using #include statements!

You bring the header file, with all of its libraries and functions, into scope for main.cpp by adding #include "main.hpp" to the very top of main.cpp:
```
#include "main.hpp"
```
Boom! Now you have access to all of the functions and libraries you stowed away in your header.

### Instructions

In the code editor, we have two files: main.cpp and main.hpp. You can navigate between them by using the tabs at the top of the page or by clicking on the folder icon directory icon.

Move the function definitions from main.cpp to main.hpp.

Oh no! The function call in main() threw an error about the functions being out of scope.

There are two problems:

* main.cpp is missing a vital #include statement to bring those functions into scope.
* main.hpp doesn't include the <iostream> library, so the functions wouldn't even compile IF they were in scope.

Let's fix this.

First, move the #include statement at the top of main.cpp to the top of main.hpp.

to_farenheit() and to_celsius are still out of scope for main().

Fix that by adding #include "main.hpp" to the top of main.cpp.

## My Code
```c++
#include <iostream>

double to_fahrenheit(int celsius) {

  double fahrenheit = (celsius * 9 / 5) + 32;
  return fahrenheit;

}

double to_celsius(int fahrenheit) {

  double celsius = (fahrenheit - 32) * 5 / 9;
  return celsius;

}

int main() {
  
  std::cout << to_fahrenheit(0) << "\n";
  std::cout << to_celsius(32) << "\n";
  
}
```
