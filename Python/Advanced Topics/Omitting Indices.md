Omitting Indices<br>
If you don't pass a particular index to the list slice, Python will pick a default.

to_five = ['A', 'B', 'C', 'D', 'E']
```python
print to_five[3:]
# prints ['D', 'E'] 

print to_five[:2]
# prints ['A', 'B']

print to_five[::2]
# print ['A', 'C', 'E']
```
The default starting index is 0.
The default ending index is the end of the list.
The default stride is 1.

**Instructions:**
Use list slicing to print out every odd element of my_list from start to finish.

Omit the start and end index. You only need to specify a stride.

Check the Hint if you need help.

**My Code:**
```python
my_list = range(1, 11) # List of numbers 1 - 10

# Add your code below!
print my_list[::2]
```
