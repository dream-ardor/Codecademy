## VARIANCE

### Square The Differences

We’re almost there! We have one small problem with our equation. Consider this very small dataset:
```
[-5, 5]
```
The mean of this dataset is 0, so when we find the difference between each point and the mean we get -5 - 0 = -5 and 5 - 0 = 5.

When we take the average of -5 and 5 to get the variance, we get 0!

Now think about what would happen if the dataset were [-200, 200]. We’d get the same result! That can’t possibly be right — the dataset with 200 is much more spread out than the dataset with 5, so the variance should be much larger!

The problem here is with negative numbers. Because one of our data points was 5 units below the mean and the other was 5 units above the mean, they canceled each other out!

When calculating variance, we don’t care if a data point was above or below the mean — all we care about is how far away it was. To get rid of those pesky negative numbers, we’ll square the difference between each data point and the mean.

Our equation for finding the difference between a data point and the mean now looks like this:

{difference} = (X−μ)
 
### Instructions

Square each of the values stored in the variables difference_one through difference_five. In Python, to square a number, use the ** operator. The code below gives you an example of squaring the variable a.
```python
squared_num = a ** 2
```

## My Code
```python
import numpy as np

grades = [88, 82, 85, 84, 90]
mean = np.mean(grades)

#When calculating these variables, square the difference.
difference_one = (88 - mean) ** 2
difference_two = (82 - mean) ** 2
difference_three = (85 - mean) ** 2
difference_four = (84 - mean) ** 2
difference_five = (90 - mean) ** 2

difference_sum = difference_one + difference_two + difference_three + difference_four + difference_five

variance = difference_sum / 5

print("The sum of the squared differences is " + str(difference_sum))
print("The variance is " + str(variance))
```
