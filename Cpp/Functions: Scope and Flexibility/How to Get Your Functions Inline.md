## How to Get Your Functions Inline

Once you set foot in the wild of C++ development, you may encounter the term “inline functions” with a couple different meanings. An inline function is a function definition, usually in a header file, qualified by inline like this:
```c++
inline 
void eat() {

  std::cout << "nom nom\n";

}
```
Using inline advises the compiler to insert the function’s body where the function call is, which sometimes helps with execution speed (and sometimes hinders execution speed). If you do use it, we recommend testing how it affects the execution speed of your program. The bottom line is inline is something you’ll probably encounter, but may never use.

However, you will sometimes also hear about “inline functions” that are just member functions (i.e. functions inside of classes — we’ll explain classes later) which have been defined and declared in a single line in a header file because the function body is so short:
```c++
// cookie_functions.hpp

// eat() belongs to the Cookie class:
void Cookie::eat() {std::cout << "nom nom\n";} 
```
Please note that you should ALWAYS add the inline keyword if you are inlining functions in a header (unless you are dealing with member functions, which are automatically inlined for you).

## Instructions

Currently, the program is set up with goodnight1()‘s declaration and definition split into night.hpp and night.cpp respectively.

We’ll try using the inline keyword and see how it affects the runtime of the function.

We’re using a library header called chrono that allows us to clock time in milliseconds. (Don’t worry if you don’t understand all of the syntax used for this!)

First, run your code as is. How many milliseconds did it take goodnight1() to execute?

Move the very short definition of goodnight1() from night.cpp over to night.hpp (replacing the declaration).

Then add the inline keyword above the function and run the code.

## My Code
```c++
#include <iostream>
#include <chrono>

#include "night.hpp"

int main() {
  
  // Measure time taken for goodnight1():
  std::chrono::high_resolution_clock::time_point start = std::chrono::high_resolution_clock::now();

  std::cout << goodnight1("tulip");
  
  std::chrono::high_resolution_clock::time_point end = std::chrono::high_resolution_clock::now();
  std::chrono::duration<double, std::milli> time_span = end - start;

  // Print time taken for goodnight1():
  std::cout << "Time taken for goodnight1(): " << time_span.count() << " milliseconds.\n\n";
  
  
  std::cout << goodnight2("eraser", "ivy");
  
}
```
