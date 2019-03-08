## FUNCTIONS

### Tackling Multiple Arguments

Hang on, you may be thinking, are you limited to one parameter per function? Not at all! You can add as many as you like, but you will have to remember their order when you call the function.
```c++
double get_tip(double price, double tip, bool total_included) {

  if (total_included) {

    return price * tip + price;

  } else {

    return price * tip;

  }

}
```
So here we have three parameters:
```
double price
double tip
bool total_included
```
When calling get_tip(), it's important to call it with price first, tip second, and return_total last:
```c++
get_tip(0.25, true, 45.50);
// this code will not work
get_tip(45.50, 0.25, true);
// this code results in 56.875, which you could round up to 56.88
```
### Instructions

Define a void function name_x_times() that takes two parameters:

* a string name
* an integer x

Inside the function body of name_x_times(), create a while loop that will run as long as x is greater than 0.

Inside the while loop, print name to the terminal.

Below the print statement, decrement (or decrease) x by 1 so that x is a smaller number on the next loop.

Now, call name_x_times() in main() with my_name and some_number as arguments.

(Don't forget to change my_name to your name!)

## My Code
```c++
#include <iostream>

// Define name_x_times() below:
void name_x_times(std::string name, int x) {
  while (x > 0) {
    std::cout << name;
    x--;
  }
  
}

int main() {
  
  std::string my_name = "Dan!";
  int some_number = 5; // Change this if you like!
  // Call name_x_times() below with my_name and some_number
  name_x_times(my_name, some_number);
  
}
```
