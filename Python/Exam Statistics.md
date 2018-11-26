EXAM STATISTICS<br>
Print those grades<br>

As a refresher, let's start off by writing a function to print out the list of grades, one element at a time.

**Instructions:**
Define a function on line 3 called print_grades with one argument, a list called grades_input.

Inside the function, iterate through grades_input and print each item on its own line.

After your function, call print_grades with the grades list as the parameter.

**MY CODE:**
```python
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5]

def print_grades(grades_input):
  for i in grades_input:
    print i
    
print print_grades(grades)
```
