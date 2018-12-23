LOOPS

Guess Number

So now that we got a demo of loops, let's write one!

The while loop looks very similar to an if statement. And just like an if statement, it executes the code inside of it if the condition is true.

However, the difference is that the while loop will continue to execute the code inside of it, over and over again, as long as the condition is true.

Here is what a while loop looks like:

while\ (condition)\ \{statements\}while (condition) {statements}
In other words, instead of executing if something is true, it executes while that thing is true.
```C++
while (guess != 8) {

  std::cout << "Wrong guess, try again: ";
  std::cin >> guess;

}
```
In this example, while guess is not equal to 8, the program will keep on asking the user to input a new number. It will exit the while loop once the user types in 8 and then the program will continue.

**Instructions:**
Inside guess.cpp, we have a program that asks the user to guess a number between 1-10 and the answer is 8!

Now instead of just asking for the user to answer it once, let's add a while loop so that they answer it up to 50 times!

The && symbol means and and it combines two conditions into one.

In this while loop, while guess does not equal to 8 and the number of tries is less than 50, we are asking the user to type a number once again. And then we add 1 to tries using the ++ operator.

**My Code:**
```C++
#include <iostream>

int main() {

  int answer = 8;
  int guess;
  
  int tries;

  std::cout << "I have a number between 1-10.\n";
  std::cout << "Please guess it: ";
  std::cin >> guess;
 
  // Write a while loop here:
   
  while (guess != 8 && tries < 50) {
    
    std::cout << "Wrong guess, try again: ";
    std::cin >> guess;
    
    tries++;
  }
 
  if (guess == 8) {
    
    std::cout << "You got it!\n";
  
  }  
  
}
```
