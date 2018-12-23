While Loop 

The last one we held your hand, so let's try one on your own.

As an example of iteration, we have the first program ever to run on a stored-program computer (the EDSAC). It was written and run by David Wheeler in the computer laboratory at Cambridge University, England, on May 6th, 1948, to calculate and print a simple list of squares like the following:
``` 
0   0
1   1
2   4
3   9
4   16
5   25
6   36
7   49
8   64
9   81
```
On the left, there are numbers from 0 to 9. On the right are their squares. For example, for the number 9, 9 * 9 = 81

**Instructions:**
In square.cpp, write this using a while loop in C++.

**My Code:**
```C++
#include <iostream>

int main() {
  
  int i = 0;
  int square = 0;
  
  // Write a while loop here:
  
  while (i < 10) {
    
    square = i * i;
    
    std::cout << i << " " << square << "\n";
    
    i++;
  }
  
}
```
