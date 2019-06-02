## Class Members

An empty class is pretty useless. Classes are designed to bring together related information and functionality — time to add stuff inside!

Components of a class are called class members. Just like you can get a string’s length using .length(), you can access class members using the dot operator (object.class_member).

There are two types of class members:

Attributes, also known as member data, consist of information about an instance of the class.
Methods, also known as member functions, are functions that you can use with an instance of the class.
We encapsulate attributes and methods in a class like this:
```C++
class City {

  // attribute
  int population;

// we'll explain 'public' later
public:
  // method
  void add_resident() {
    population++;
  }

};
```
Unless you have a really empty class, it’s common to declare methods inside the class (in a header), then define them outside the class (in a .cpp file of the same name). You can do this using ClassName:: before the method name to indicate its class like this:
```C++
int City::get_population() {
  return population;
}
```
Unlike with regular functions, you will need to include the header file in the .cpp file where you define the methods.

Note: The method must also be declared inside the class if you want to define it outside.

## Instructions

Add a Song class to song.hpp. Inside the class, add an std::string attribute called title.

Below title, add public: on a new line. We’ll explain this part later.

Add two method declarations for Song underneath:

.add_title(), a void method which accepts a new_title for a song. (Make sure this parameter has a different name than title.)
.get_title(), which has no parameters and will return as std::string.

Move over to song.cpp. Add definitions for each method:

Song::add_title() should set title to new_title.
Song::get_title() should return title.

```c++
#include <string>

// add the Song class here:
class Song {
  
  std::string title;

public:
  void add_title(std::string new_title);
  std::string get_title();
  
};
```
