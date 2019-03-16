## VARIANCE

### Average Distances

We now have five different values that describe how far away each point is from the mean. That seems to be a good start in describing the spread of the data. But the whole point of calculating variance was to get one number that describes the dataset. We don’t want to report five values — we want to combine those into one descriptive statistic.

To do this, we’ll take the average of those five numbers. By adding those numbers together and dividing by 5, we’ll end up with a single number that describes the average distance between our data points and the mean.

Note that we’re not quite done yet — our final answer is going to look a bit strange here. There’s a small problem that we’ll fix in the next exercise.

### Instructions

Sum the five variables difference_one through difference_five and store the result in the variable difference_sum.

Divide difference_sum by 5 and store the result in the variable named average_difference.

Think about the answer. Do you think it accurately captures the spread of your data?

## My Code
```python
import numpy as np

grades = [88, 82, 85, 84, 90]
mean = np.mean(grades)

difference_one = 88 - mean
difference_two = 82 - mean
difference_three = 85 - mean
difference_four = 84 - mean
difference_five = 90 - mean

#Part 1: Sum the differences
difference_sum = difference_one + difference_two + difference_three + difference_four + difference_five

#Part 2: Average the differences
average_difference = difference_sum / 5

#IGNORE CODE BELOW HERE
print("The sum of the differences is " + str(format(difference_sum, "f")))
print("The average difference is " + str(format(average_difference, "f")))
```
