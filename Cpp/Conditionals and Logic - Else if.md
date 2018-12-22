Conditionals and Logic - Else If statement

**Instructions:**
In chemistry, pH is a scale used to specify the acidity or basicity of an aqueous solution.

Write an if, else if, else statement that:

If ph is greater than 7, output "Basic".
If ph is less than 7, output "Acidic".
If neither, output "Neutral".
Remember to take a look at the hint if you are stuck.

**My Code:**
```C++
#include <iostream>

int main() {
  
  double ph = 4.6;
  
  // Write the if, else if, else here:
  
  if (ph > 7) {
    std::cout << "Basic\n";
  }
  
  else if (ph < 7) {
    std::cout << "Acidic\n";

  }
  
  else {
    std::cout << "Neutral\n";
  }
    
}
```
