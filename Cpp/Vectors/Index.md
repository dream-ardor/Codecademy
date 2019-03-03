## VECTORS

### Index

Now that we have a vector, how do we access an indivual element? This is where index comes into play.

An index refers to an element's position within an ordered list. Vectors are 0-indexed, meaning the first element has index 0, the second index 1, and so on.

For example, suppose we have a char vector with all the vowels:
```c++
std::vector<char> vowels = {'a', 'e', 'i', 'o', 'u'};
```
It should look something like this:

vowels

The character at index 0 is 'a'.
The character at index 1 is 'e'.
The character at index 2 is 'i'.
The character at index 3 is 'o'.
The character at index 4 is 'u'.

To output each of the elements, we can do:
```c++
std::cout << vowels[0] << "\n";
std::cout << vowels[1] << "\n";
std::cout << vowels[2] << "\n";
std::cout << vowels[3] << "\n";
std::cout << vowels[4] << "\n";
```
Using the notation vector[index] with square brackets after the vector name and the element's index number inside.

This will output:

a
e
i
o
u
### Instructions:
What is the element at index 2 in the subway_child vector?

Find out the answer by outputting it out using std::cout.

## My Code
```c++
#include <iostream>
#include <vector>

int main() {
   
  std::vector<double> subway_adult = {800, 1200, 1500};
  
  std::vector<double> subway_child = {400, 600, 750};
  
  // What number at index 2 of subway_child?
  std::cout << subway_child[2];
  
}
```
