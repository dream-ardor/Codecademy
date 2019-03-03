## VECTORS

Initializing a Vector

Now we know how to create a vector, we can also initialize a vector, giving it values, as we are creating it in the same line.

For example, instead of just creating a double vector named location:
```c++
std::vector<double> location;
```
We can create and initialize location with specific values:
```c++
std::vector<double> location = {42.651443, -73.749302};
```
Here, we are storing a latitude and a longitude.

So it would look something like this:

Vector

Another way we can initialize our vector is by presizing, or setting the size.

Suppose we want to create and initialize a vector with two elements. However, we don't know what values we want to add yet:
```c++
std::vector<double> location(2);
```
Here, we are creating a double vector and setting the initial size to 2 using parentheses.

It would look something like this:

presize

Because 0.0 is the default value for double.

### Instructions:

Suppose the Tokyo Subway costs are as follows:

Ticket	Adult	Child
24-hour	¥800	¥400
48-hour	¥1200	¥600
72-hour	¥1500	¥750

We have initialized the subway_adult already for you.

Initialize the subway_child vector with:

400
600
750
Note: The vector can still be double even though the values entered are ints.

## My Code
```c++

#include <iostream>
#include <vector>

int main() {
   
  std::vector<double> subway_adult = {800, 1200, 1500};
  
  // Give subway_child some values:
  
  std::vector<double> subway_child = {400, 600,  750};
  
}

```
