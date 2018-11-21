PRACTICE MAKES PERFECT<br>
reverse<br>
Great work so far! Let's practice writing some functions that work with strings.

**INSTRUCTIONS:**
Define a function called reverse that takes a string textand returns that string in reverse. For example: reverse("abcd") should return "dcba".

You may not use reversed or [::-1] to help you with this.

You may get a string containing special characters (for example, !, @, or #).

**SOLUTION:**
```python
def reverse(text):
    a=""
    for i in text:
        a = i + a
        print a 
    return a
```
