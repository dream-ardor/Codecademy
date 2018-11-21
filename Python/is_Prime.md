PRACTICE MAKES PERFECT<br>
is_prime<br>
A prime number is a positive integer greater than 1 that has no positive divisors other than 1 and itself. (That's a mouthful!)

In other words, if you want to test if a number in a variable x is prime, then no other number should go into x evenly besides 1 and x. So 2 and 5 and 11 are all prime, but 4 and 18 and 21 are not.

If there is a number between 1 and x that goes in evenly, then x is not prime.

**INSTRUCTIONS:**
Define a function called is_prime that takes a number x as input.

For each number n from 2 to x - 1, test if x is evenly divisible by n.

If it is, return False.

If none of them are, then return True.

**SOLUTION:**
```python
def is_prime(x):
    if x < 2:
        return False
    for n in range(2, x):
        if x % n == 0:
            return False 
    else:
        return True
```
