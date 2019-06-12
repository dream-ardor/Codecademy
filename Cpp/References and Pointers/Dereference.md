## Dereference

So now we learned what a pointer is and how to create one, but is there a way to obtain the value pointed to by the pointer?

The asterisk sign * a.k.a. the dereference operator is used to obtain the value pointed to by a variable. This can be done by preceding the name of a pointer variable with *.
```c++
int blah = *ptr;
```
The double meaning of the * symbol can be tricky at first, so make sure to note:

* When * is used in a declaration, it is creating a pointer.
* When * is not used in a declaration, is is a dereference operator.

## Instructions

Print out *ptr using std::cout.

What do you think it will output?

## My Code
```c++
#include <iostream>

int main() {
  
  int power = 9000;
  
  // Create pointer
  int* ptr = &power;
  
  // Print ptr
  std::cout << ptr << "\n";
  
  // Print *ptr
  std::cout << *ptr;
  
}
```
