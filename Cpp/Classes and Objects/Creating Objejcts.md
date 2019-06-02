## Creating Objects

Now that you have a class, let’s create some objects! To refresh your memory, an object is an instance of a class, which encapsulates data and functionality pertaining to that data.

To create (or instantiate) an object, we can do this:
```c++
City accra;
```
We can give the object’s attributes values like this (note that these must be attributes you defined in the class):
```
accra.population = 2270000;
```
Later, we can access this information using the method we added to the City class (if it’s in a public part of the class):
```
accra.get_population();
```
## Instructions

Flip over to song.hpp and song.cpp to see how the class and its methods are set up.

Then, in music.cpp, instantiate a new song electric_relaxation in main().

Use Song‘s built-in .add_title() method to add a title to electric_relaxation: "Electric Relaxation".

Use .get_title() to retrieve electric_relaxations title and print it to the terminal.

```c++
#include <iostream>
#include "song.hpp"

int main() {

  Song electric_relaxation;
  electric_relaxation.add_title("Electric Relaxation");
  std::cout << electric_relaxation.get_title();
  
}
```
