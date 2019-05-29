## Getting a Header Yourself

If your program keeps growing, you may have to scroll through many declarations before you see main(). That doesn’t seem like the best way to do things. Plus you don’t want to keep declaring the same functions over and over for different files — making changes would be incredibly tiresome!

Well, you can take those function declarations and move them all over to a header file, another file — usually with the same name as the file with all of the function definitions — with the extension .hpp or .h. For example, if your function definitions are in my_functions.cpp, the corresponding header file would be my_functions.hpp or my_functions.h.

So how do you bring everything from a header file into scope for another file? Do you just link the header in the compilation statement like you did with the second .cpp file?

As it turns out, with headers, you can just add #include "my_functions.hpp" to the very top of main.cpp:

#include "my_functions.hpp"
Boom! This line pastes in everything from my_functions.hpp. Now you have access to all of the function declarations you stowed away in your header.

## Instructions

Move the function declarations from above main() in main.cpp into fns.hpp.

Compile and execute.

Did that work?

No! Why not?

We forgot to include the header file in main.cpp. Without the include statement, the program doesn’t know that any of the functions even exist.

Add the include statement above main().

Now compile and execute again. Remember to link the two .cpp files when compiling.

Does it work?

## main.cpp
```c++
#include <iostream>
#include "fns.hpp"

int main() {
  
  std::cout << is_palindrome("noon") << "\n";
  std::cout << tenth_power(4) << "\n";
  std::cout << average(4.0, 7.0) << "\n";
  
}
```

## fns.hpp
```c++
// Move function declarations here:
double average(double num1, double num2);
int tenth_power(int num);
bool is_palindrome(std::string text);

```
## bash
```bash
g++ main.cpp fns.cpp

./a.out
```
