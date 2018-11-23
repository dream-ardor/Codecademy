PRACTICE MAKES PERFECT<br>
purify<br>

Awesome! Now let's practice filtering a list.

**Instructions:**
Define a function called purify that takes in a list of numbers, removes all odd numbers in the list, and returns the result. For example, purify([1,2,3]) should return [2].

Do not directly modify the list you are given as input; instead, return a new list with only the even numbers.

**SOLUTION:**
```python
def purify(numbers):
    return [a for a in numbers if a % 2 == 0]
```
