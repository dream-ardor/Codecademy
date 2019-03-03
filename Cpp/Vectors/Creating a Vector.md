## VECTORS

Creating a Vector

The std::vector lives in the <vector> header. So first, we need to add this line of code at the top of the program:
```c++
#include <vector>
```
For review, #include is a preprocessor directive that tells the compiler to include whatever library that follows. In our case that is the standard vector library.

And the syntax to create a vector looks like:
```c++
std::vector<type> name;
```
So to define a vector of ints called calories_today:
```c++
std::vector<int> calories_today;
```
Inside the angle brackets is the data type of the vector. After the angle brackets is the name of the vector.

Note: The type of the vector (i.e., what data type is stored inside) cannot be changed after the declaration.

## Instructions

The Tokyo Subway has different payment options for adults and children. We have declared a double vector already named subway_adult.

Declare another double vector named subway_child.

## My Code
```c++
#include <iostream>
#include <vector>

int main() {
   
  std::vector<double> subway_adult;
  // Declare another vector here:
  std::vector<double> subway_child;
  
}
```
