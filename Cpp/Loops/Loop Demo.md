While Loop Demo

So first up... the while loop!

Before we dive deep into the syntax of the while loop, let's do a demo.

Inside enter_pin.cpp, we have a program that asks and checks for a password. It uses a while loop to ask the user for the password over and over again.

Note: You don't need to understand the code right now.

**Instructions:**
Compile and execute using the terminal.

When the program asks you to Enter your PIN:, try the following:

Press 1111 and press enter.

Press 2019 and press enter.

Press 1234 and press enter.

```C++
#include <iostream>

int main() {
  
  int pin = 0;
  int tries = 0;
  
  std::cout << "BANK OF CODECADEMY\n";
  
  std::cout << "Enter your PIN: ";
  std::cin >> pin;
  
  while (pin != 1234 && tries <= 3) {
    
    std::cout << "Enter your PIN: ";
    std::cin >> pin;
    tries++;
    
  }
  
  if (pin == 1234) {
    
    std::cout << "PIN accepted!\n";
    std::cout << "You now have access.\n"; 
    
  }
  
}
```
**My Code:**
```bash
g++ enter_pin.cpp
./a.out
```
