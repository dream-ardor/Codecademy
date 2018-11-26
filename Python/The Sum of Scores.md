EXAM STATISTICS<br>
The sum of scores<br>

Now that we have a function to print the grades, let's create another function to compute the sum of all of the test grades.

This will be super-helpful when we need to compute the average score.

I know what you're thinking, "let's just use the built-in sum function!" The built-in function would work beautifully, but it would be too easy.

Computing the sum manually involves computing a rolling sum. As you loop through the list, add the current grade to a variable that keeps track of the total, let's call that variable total.

**Instructions:**
On line 3, define a function, grades_sum, that does the following:

Takes in a list of scores, scores
Computes the sum of the scores
Returns the computed sum.
Call the newly created grades_sum function with the list of grades and print the result.

**MY CODE:**
```python
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5]

def grades_sum(scores):
  total = 0
  for i in scores:
    total = total + i
  return total
    
print grades_sum(grades)
```
