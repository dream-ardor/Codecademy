## FUNCTIONS

#### The Function of Functions

As a programmer, you will find yourself reusing the same blocks of code over and over throughout your program. In times like these, you can turn to functions.

Also known as a method or procedure, a function is a named group of code statements that accomplish something together, a bit like a factory machine.

make_sandwich() adds ingredients together to make a sandwich
There are some great reasons to use functions in your code:

A single line can make all that code fire off instead of a whole bunch of lines (it's pretty fantastic).
You can build DRY (Don't Repeat Yourself) code, reusing the code you already wrote.
Functions help make your code flexible and modular, meaning you can group your code more easily by task.
In fact, every C++ program has at least one function. "Hold on," you may be thinking, "I've written some C++ programs, but I haven't written any functions yet!"

Well, as it happens, main() is a function that you've already used! And you'll understand it a bit more as you learn how functions work.

### Instructions

Take a look at the IT support conversations in main.cpp. There's a lot of repeating code.

Compile and execute the code. It works, but we could make this code much shorter and cleaner with the help of a function...

## My Code
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

//compile and execute: g++ main.cpp - ./a.out
```
