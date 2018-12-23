LOOPS

99 Bottles

In the last exercise, we saw an example of an incrementing for loop so here we are going to show you how to write a for loop where the counter goes down. When we know exactly how many times we want to iterate (or when we are counting), we can use a for loop instead of a while loop:

Incrementing for loop:
```C++
for (int i = 0; i < 20; i++) 
{
  // Statements
}
```
```C++
Decrementing for loop:

for (int i = 20; i > 0; i--) 
{
  // Statements
}
```
**Instructions:**
Write a 99bottles.cpp program that prints the verses of the "99 Bottles" song. Each stanza goes something like this:
```
n bottles of pop on the wall.
Take one down and pass it around.
n-1 bottles of pop on the wall.
```
Hint: Use a decrementing for loop!

**Solution:**
```C++
#include <iostream>

int main() {

  // Write a for loop here:
  
  for (int i = 99; i > 0; i--) {

    std::cout << i << " bottles of pop on the wall.\n";
    std::cout << "Take one down and pass it around.\n";
    std::cout << i - 1 << " bottles of pop on the wall.\n\n";
      
  }
  
   std::cout << "No more bottles of pop on the wall.\n";
  std::cout << "No more bottles of pop.\n";
  std::cout << "Go to the store and buy some more,\n";
  std::cout << "99 bottles of pop on the wall.\n";
}
```
