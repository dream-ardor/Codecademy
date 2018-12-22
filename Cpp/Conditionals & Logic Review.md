CONDITIONALS & LOGIC

Review

Congratulations! Congrats!

Here are some of the major concepts:

* An if statement checks a condition and will execute a task if that condition evaluates to true.
* if / else statements make binary decisions and execute different code blocks based on a provided condition.
* We can add more conditions using else if statements.
* Relational operators, including <, >, <=, >=, ==, and != can compare two values.
* A switch statement can be used to simplify the process of writing multiple else if statements. The break keyword stops the remaining cases from being checked and executed in a switch statement.
* Download the C++ Reference Guide: Conditionals & Logic (Coming Soon!) to help you remember the content covered in this lesson.

**Instructions:**
Optional: Little Mac is an interplanetary space boxer, who is trying to win championship belts for various weight categories on other planets within the solar system.

Write a program that helps him keep track of his target weight by:

It should ask him what his earth weight is.
Ask him to enter a number for the planet he wants to fight on.
It should then compute his weight on the destination planet.

**Solution:**
```C++
#include <iostream>

int main() {
  
  double weight;
  int x;

  std::cout << "Please enter your current earth weight: ";
  std::cin >> weight;

  std::cout << "\nI have information for the following planets:\n\n";
  std::cout << "   1. Venus   2. Mars    3. Jupiter\n";
  std::cout << "   4. Saturn  5. Uranus  6. Neptune\n\n";

  std::cout << "Which planet are you visiting? ";
  std::cin >> x;

  if (x == 1) {

    weight = weight * 0.78;

  } else if (x == 2) {

    weight = weight * 0.39;

  } else if (x == 3) {

    weight = weight * 2.65;

  } else if (x == 4) {

    weight = weight * 1.17;

  } else if (x == 5) {
    
     weight = weight * 1.05;

  } else if (x == 6) {

    weight = weight * 1.23;

  }

  std::cout << "\nYour weight: " << weight << "\n";

  
}
```
