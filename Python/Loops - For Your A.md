**LOOPS**<br>
For your A<br>

String manipulation is useful in for loops if you want to modify some content in a string.
The``` ,``` character after our print statement means that our next print statement keeps printing on the same line.

**CODE**
```python
phrase = "A bird in the hand..."

# Add your for loop
for char in phrase:
  if char.lower() == "a":
    print "X",
  else:
      print char,
```
