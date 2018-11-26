EXAM STATISTICS<br>
Computing the Average<br>
The average test grade can be found by dividing the sum of the grades by the total number of grades.

Luckily, we just created an awesome function, grades_sum to compute the sum.

**Instructions:**

Define a function, grades_average, below the grades_sum function that does the following:

Has one argument, grades_input, a list
Calls grades_sum with grades_input
Computes the average of the grades by dividing that sum by float(len(grades_input)).
Returns the average.
Call the newly created grades_average function with the list of grades and print the result.

**MY CODE:**
```python
grades = [100, 100, 90, 40, 80, 100, 85, 70, 90, 65, 90, 85, 50.5]

def grades_sum(scores):
  total = 0
  for i in scores:
    total = total + i
  return total
    
print grades_sum(grades)
  
def grades_average(grades_input):
  total = grades_sum(grades_input)
  return float(total) / len(grades_input)
print grades_average(grades)
```
