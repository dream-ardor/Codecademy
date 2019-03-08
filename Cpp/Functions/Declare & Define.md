## FUNCTIONS

### Declare & Define

Often, built-in functions aren't enough to tackle the wide array of programming challenges out there. But never fear: you can write your own functions too!

A C++ function is comprised of two distinct parts:

Declaration: this includes the function's name, what the return type is, and any parameters (if the function will accept input values, known as arguments).

Definition: also known as the body of the function, this contains the instructions for what the function is supposed to do.
This is the overall structure:
```c++
return_type function_name( any, parameters, you, have ) {

   // Code block here

   return output_if_there_is_any;

}
```
This is what it might look like with real code:
```c++
void make_sandwich() {

  std::cout << "bread\n";
  std::cout << "egg\n";
  std::cout << "cheese\n";
  std::cout << "avocado\n";
  std::cout << "bread\n";

}
```
### Instructions

Watch how the make_sandwich() function gets executed step by step!

This is just a preview of how everything works, so don't worry about memorizing anything. In the next exercise, we'll start building functions from scratch...
