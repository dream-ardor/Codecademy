## Water Plant

needs_water()

## Instructions

Define a function needs_water() that accepts:

* An int number of days since the previous watering.
* A bool value is_succulent. (A value of true would indicate that the plant is a succulent.) Inside the function, you’ll need some conditional logic:
* If is_succulent is false and days is greater than 3, return "Time to water the plant.".
* If is_succulent is true and days is 12 or less, return "Don't water the plant!".
* If is_succulent is true and days is greater than or equal to 13, return "Go ahead and give the plant a little water.".

Otherwise, return "Don't water the plant!".
Note: Don’t print the strings; return them from the function.

## Solution
```c++
#include <iostream>

// Define needs_water() here:
std::string needs_water(int days, bool is_succulent) {
  
  if (days > 3 && is_succulent == false) {
    return "Time to water the plant.";
  } else if (days < 13 && is_succulent) {
    return "Don't water the plant!";
  } else if (days >= 13 && is_succulent) {
    return "Go ahead and give the plant a little water.";
  } else {
    return "Don't water the plant!";
  }
  
}

int main() {
  
  std::cout << needs_water(10, false) << "\n";
  
}
```
