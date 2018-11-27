keys() and values()<br>
While .items() returns an array of tuples with each tuple consisting of a key/value pair from the dictionary:

The .keys() method returns a list of the dictionary's keys, and
The .values() method returns a list of the dictionary's values.
Again, these methods will not return the keys or values from the dictionary in any specific order.

You can think of a tuple as an immutable (that is, unchangeable) list. Tuples are surrounded by ()s and can contain any data type.

**Instructions:**
Remove your call to .items() and replace it with a call to .keys() and a call to .values(), each on its own line. Make sure to print both!

**MY CODE:**
```python
my_dict = {
  "Name": "Dan",
  "Age": 38,
  "Is very handsome?": True
}

print my_dict.keys()
print my_dict.values()
```
