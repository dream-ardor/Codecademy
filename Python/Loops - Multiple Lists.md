**LOOPS**<br>
Multiple lists<br>
It's also common to need to iterate over two lists at once. This is where the built-in zip function comes in handy.

zip will create pairs of elements when passed two lists, and will stop at the end of the shorter list.

zip can handle three or more lists as well!

**Instructions:**
Compare each pair of elements and print the larger of the two.

**MY CODE**
```python
list_a = [3, 9, 17, 15, 19]
list_b = [2, 4, 8, 10, 30, 40, 50, 60, 70, 80, 90]

for a, b in zip(list_a, list_b):
  print max(a,b)
```
