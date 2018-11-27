Iterators for Dictionaries<br>
Let's start with iterating over a dictionary. Recall that a dictionary is just a collection of keys and values.
```python
d = {
  "Name": "Guido",
  "Age": 56,
  "BDFL": True
}
print d.items()
# => [('BDFL', True), ('Age', 56), ('Name', 'Guido')]
```
Note that the .items() method doesn't return key/value pairs in any specific order.

**Instructions:**
Create your own Python dictionary, my_dict, in the editor to the right with two or three key/value pairs.

Then, print the result of calling the my_dict.items().

**MY CODE:**
```python
my_dict = {
  "Name": "Dan",
  "Age": 38,
  "Is very handsome?": True
}

print my_dict.items()
```
