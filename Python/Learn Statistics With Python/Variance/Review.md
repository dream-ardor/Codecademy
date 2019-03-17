## VARIANCE

### Review

Great work! In this lesson you’ve learned about variance and how to calculate it.

In the example used in this lesson, the importance of variance was highlighted by showing data from test scores in classes taught by two different teachers. What story does variance tell? What conclusions can we draw from this statistic?

The histogram of scores from two different teacher's classes
In the class with low variance, it seems like the teacher strives to make sure all students have a firm understanding of the subject, but nobody is exemplary.

In the class with high variance, the teacher might focus more of their attention on certain students. This might enable some students to ace their tests, but other students get left behind.

If we only looked at statistics like mean, median, and mode, these nuances in the data wouldn’t be represented.

### Instructions

You might be wondering why we need to compute the variance. After all, by comparing histograms, it was fairly easy to tell which dataset had a larger spread.

Variance is useful because it is a measure of spread. While we might get a general understanding of the spread by looking at a histogram, computing the variance gives us a numerical value that helps us describe the level of confidence of our comparison.

It is also interesting to consider datasets that don’t have the same general curve.

Run the code to see two datasets that have a similar mean, but look very different. You’ll also see a printout of their mean and variance. Before looking at the printout, try to guess which dataset has a larger variance.
```python
script.py

import numpy as np
import matplotlib.pyplot as plt
import codecademylib3_seaborn
from data import dataset_one, dataset_two

plt.hist(dataset_one, alpha =0.75, label = "dataset_one", bins = 80)
plt.hist(dataset_two, alpha = 0.5, label = "dataset_two", bins = 80)
plt.legend()

print("The mean of the first dataset is " + str(np.mean(dataset_one)))
print("The mean of the second dataset is " + str(np.mean(dataset_two)) + "\n")

print("The variance of the first dataset is " + str(np.var(dataset_one)))
print("The variance of the second dataset is " + str(np.var(dataset_two)))

plt.show()
```
