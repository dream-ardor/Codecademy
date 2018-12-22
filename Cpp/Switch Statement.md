CONDITIONALS & LOGIC

Switch Statement

Now that we know how if, else if, else work, we can write programs that have multiple outcomes. Programs with multiple outcomes are so common that C++ provides a special statement for it... the switch statement!

A switch statement provides an alternative syntax that is easier to read and write. A switch statement looks like this:
```C++
switch (grade) {

  case 9:
    std::cout << "Freshman\n";
    break;
  case 10:
    std::cout << "Sophomore\n";
    break;
  case 11:
    std::cout << "Junior\n";
    break;
  case 12:
    std::cout << "Senior\n";
    break;
  default:
    std::cout << "Invalid\n";
    break;

}
```
The switch keyword initiates the statement and is followed by (), which contains the value that each case will compare. In the example, the value or expression of the switch statement is grade.
Inside the block, {}, there are multiple cases.
The case keyword checks if the expression matches the specified value that comes after it. The value following the first case is 9. If the value of grade is equal to 9, then the code that follows the : would run.
The break keyword tells the computer to exit the block and not execute any more code or check any other cases inside the code block.
At the end of each switch statement, there is a default statement. If none of the cases are true, then the code in the default statement will run. It's essentially the else part.
In the code above, suppose grade is equal to 10, then the output would be "Sophomore".

Note: Without the break keyword at the end of each case, the program would execute the code for all matching cases and the default code as well. This behavior is different from if / else conditional statements which execute only one block of code.

**Instructions:**
Inside pokedex.cpp, we have a switch statement!

Let's add 3 more cases right before default:

case 7 that outputs "Squirtle"
case 8 that outputs "Wartortle"
case 9 that outputs "Blastoise"

**My Code:**
```C++
#include <iostream>

int main() {
  
  int number = 9;
  
  switch(number) {
    
    case 1 :
      std::cout << "Bulbusaur\n";
      break;
    case 2 :
      std::cout << "Ivysaur\n";
      break;
    case 3 :
      std::cout << "Venusaur\n";
      break;
    case 4 :
      std::cout << "Charmander\n";
      break;
    case 5 :
      std::cout << "Charmeleon\n";
      break;
    case 6 :
      std::cout << "Charizard\n";
      break;
    case 7:
      std::cout << "Squirtle\n";
      break;
    case 8:
      std::cout << "Wartortle\n";
      break;
    case 9:
      std::cout << "Blastoise\n";
      break;
    default :
      std::cout << "Unknown\n";
      break;
  
  }
  
}
```
