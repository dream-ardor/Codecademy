Now You Try!<br>
Great work! Now it's time for you to create a list comprehension all on your own.
```python
c = ['C' for x in range(5) if x < 3]
print c
```
The example above creates and prints out a list containing ['C', 'C', 'C'].

**Instructions:**
Use a list comprehension to create a list, cubes_by_four.

The comprehension should consist of the cubes of the numbers 1 through 10 only if the cube is evenly divisible by four.

Finally, print that list to the console.

Note that in this case, the cubed number should be evenly divisible by 4, not the original number.

**MY CODE:**
```python
cubes_by_four= [i**3 for i in range(1,11) if i**3 % 4 == 0]
print cubes_by_four
```
