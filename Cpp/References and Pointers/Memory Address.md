## Memory Address

So we haved learned about references (aliases), which are created by using the & symbol in a variable declaration. But the & sign can have another meaning.

The “address of” operator, &, is used to get the memory address, the location in the memory, of an object.

Suppose we declare a variable called:
```c++
int porcupine_count = 3;
```
Have you wondered where the variable porcupine_count is stored on the computer? We can find out by printing out &porcupine_count:
```c++
std::cout << &porcupine_count << "\n";
```
It will return something like:

0x7ffd7caa5b54

This is a memory address represented in hexadecimal. A memory address is usually denoted in hexadecimal instead of binary for readability and conciseness.

The double meaning of the & symbol can be tricky at first, so make sure to note:

* When & is used in a declaration, it is a reference operator.
* When & is not used in a declaration, it is an address operator.

## Instructions

In the code editor, we have already declared and initialized a varialbe called power.

Print the memory address of power using std::cout.

## My Code
```c++
#include <iostream>

int main() {
  
  int power = 9000;
  
  // Print power
  std::cout << power << "\n";
  
  // Print &power
  
  std::cout << &power << "\n";
}
```
