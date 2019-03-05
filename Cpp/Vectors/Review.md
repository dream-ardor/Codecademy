## VECTORS

Review

Congratulations! You have learned about how to store groups of data into vectors in C++. 🙌

Here are some of the things that we learned:

Vectors are a sequence of elements that you can access by an index.
```c++
std::vector<int> even = {2, 4, 6, 8, 10};
```
The first index in a vector is 0.

Some of the functions that come with vectors:
```c++
.push_back()
.pop_back()
.size()
```
We can use a for loop to iterate through a vector.

### Instructions

Optional: Write a program to find the sum of even numbers and the product of odd numbers in a vector.

For example:

Suppose we have a vector that is {2, 4, 3, 6, 1, 9}.

Then the program should output:
```
Sum of even numbers is 12
Product of odd numbers is 27
```

## My Code
```c++
#include <iostream>
#include <vector>

int main() {

  int total_even = 0;
  int product_odd = 1;

  std::vector<int> vector = {2, 4, 3, 6, 1};

  for (int i = 0; i < vector.size(); i++) {

    if (vector[i] % 2 == 0) {

      total_even = total_even + vector[i];

    } else {

      product_odd = product_odd * vector[i];

    }

  }

  std::cout << "Sum of even: " << total_even << "\n";
  std::cout << "Product of odd: " << product_odd;

}
```
