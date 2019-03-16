## VARIANCE

### Variance

Finding the mean, median, and mode of a dataset is a good way to start getting an understanding of the general shape of your data

However, those three descriptive statistics only tell part of the story. Consider the two datasets below:
```python
dataset_one = [-4, -2, 0, 2, 4]
dataset_two = [-400, -200, 0, 200, 400]
```

These two datasets have the same mean and median — both of those values happen to be 0. If we only reported these two statistics, we would not be communicating any meaninful difference between these two datasets.

This is where variance comes into play. Variance is a descriptive statistic that describes how spread out the points in a data set are.

### Instructions

Run the code and take a look at the two histograms that get created. Also look at the mean of each dataset.

These two histograms show the test grades of students from two different teacher’s classes. While the datasets have very similar means, their variances are very different. Think about the following questions:

* Which dataset looks the most spread out?
* When looking at the spread of a histogram, why are the units on the x-axis so important?
* What does the spread of the data tell you about these two teachers that you might not understand if you only looked at the mean?

```python
script.py

import numpy as np
import matplotlib.pyplot as plt
import codecademylib3_seaborn

teacher_one_grades = [83.42, 88.04, 82.12, 85.02, 82.52, 87.47, 84.69, 85.18, 86.29, 85.53, 81.29, 82.54, 83.47, 83.91, 86.83, 88.5, 84.95, 83.79, 84.74, 84.03, 87.62, 81.15, 83.45, 80.24, 82.76, 83.98, 84.95, 83.37, 84.89, 87.29]
teacher_two_grades = [85.15, 95.64, 84.73, 71.46, 95.99, 81.61, 86.55, 79.81, 77.06, 92.86, 83.67, 73.63, 90.12, 80.64, 78.46, 76.86, 104.4, 88.53, 74.62, 91.27, 76.53, 94.37, 84.74, 81.84, 97.69, 70.77, 84.44, 88.06, 91.62, 65.82]

print("Teacher One mean: " + str(np.mean(teacher_one_grades)))
print("Teacher Two mean: " + str(np.mean(teacher_two_grades)))

plt.subplot(211)
plt.title("Teacher One Grades")
plt.xlabel("Grades")
plt.hist(teacher_one_grades)
plt.xlim(65, 105)


plt.subplot(212)
plt.title("Teacher Two Grades")
plt.xlabel("Grades")
plt.hist(teacher_two_grades, bins = 20)
plt.xlim(65, 105)

plt.tight_layout()
plt.show()
```
