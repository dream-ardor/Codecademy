## Tenth Power
tenth_power()

## Instructions

Write a function named tenth_power() that has:

An int parameter named num.

The function should return num raised to the 10th power.

## Solution
```c++
#include <iostream>
#include <cmath>

// Define tenth_power() here:
int tenth_power(int num) {
 num = num * num * num * num * num * num * num * num * num * num;
  return num;
  
}

int main() {
  
  std::cout << tenth_power(0) << "\n";
  std::cout << tenth_power(1) << "\n";
  std::cout << tenth_power(2) << "\n";
  
}
```
