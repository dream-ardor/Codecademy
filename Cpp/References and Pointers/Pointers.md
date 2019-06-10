## Pointers

In C++, a pointer variable is mostly the same as other variables, which can store a piece of data. Unlike normal variables, which store a value (such as an int, double, char), a pointer stores a memory address.

While references are a newer mechanism that originated in C++, pointers are an older mechnaism that was inherited from C. We recommend avoiding pointers as much as possible; usually, a reference will do the trick. However, you will see pointers a lot in the wild, particularly in older projects, where they are used in a very similar way to references.

Pointers must be declared before they can be used, just like a normal variable. They are syntactically distinguished by the *, so that int* means “pointer to int“ and double* means “pointer to double“.
```c++
int* number;
double* decimal;
char* character;
```
So suppose we have a variable called gum:
```c++
int gum = 8;
```
We can create a pointer to it by:
```c++
int* ptr = &gum;
int* makes it a pointer rather than a normal variable.
ptr is the pointer name.
&gum is the memory address of the other variable gum.
```
So now ptr has a value of gum‘s memory address.

Pointers:
Note: Syntactically, spaces around * do not matter, but the best practice is to have it after the data type.
```c++
int* number;
int *number;
int * number;
```
## Instructions

In the code editor, we have already declared and initialized a variable called power.

Create a pointer called ptr that points to the memory address of power.

Now let’s output the ptr using std::cout.

## My Code
```c++
#include <iostream>

int main() {
  
  int power = 9000;
  
  // Create pointer
  int* ptr = &power;
  
  // Print ptr
  std::cout << ptr;
  
}
```
