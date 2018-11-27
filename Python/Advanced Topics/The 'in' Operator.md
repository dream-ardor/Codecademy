The 'in' Operator<br>
For iterating over lists, tuples, dictionaries, and strings, Python also includes a special keyword: in. You can use in very intuitively, like so:
```python
for number in range(5):
  print number,

d = { 
  "name": "Eric",
  "age": 26
}

for key in d:
  print key, d[key],

for letter in "Eric":
  print letter,  # note the comma!
  ```
In the example above, first we create and iterate through a range, printing out 0 1 2 3 4. Note that the trailing comma ensures that we keep printing on the same line.
Next, we create a dictionary and iterate through, printing out age 26 name Eric. Dictionaries have no specific order.
Finally, we iterate through the letters of a string, printing out E r i c.

**Instructions:**
For each key in my_dict: print out the key , then a space, then the value stored by that key. (You should use print a, b rather than print a + " " + b.)

**MY CODE:**
```python
my_dict = {
  "Name": "Dan",
  "Age": 38,
  "Is very handsome?": True
}

for key in my_dict:
  print key, my_dict[key]
```
