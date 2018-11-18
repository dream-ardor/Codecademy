**LOOPS**<br>
Change it up

As mentioned, the else block won't run in this case, since break executes when it hits 'tomato'.

**Instructions:**
Modify the code in the editor such that the for loop's else statement is executed.

**MY CODE:**
```python
fruits = ['banana', 'apple', 'orange', 'tomato', 'pear', 'grape']

print 'You have...'
for f in fruits:
  if f == 'kiwi':  #changed from 'tomato' so that the else statement prints 
    print 'A tomato is not a fruit!' # (It actually is.)
    break
  print 'A', f
else:
  print 'A fine selection of fruits!'
  ```
