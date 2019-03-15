## MODE

### Introduction

In this lesson, you will learn how to find the mode of a dataset. Each of the next three exercises will cover the following:

* Manually finding the mode of a dataset
* Using Python’s SciPy library to find the mode
* Comparing mode to mean and median values

In the lesson, we will use a dataset of the 100 greatest novels, determined by a French literary magazine, Le Monde. From the dataset, you will use the mode to answer the question:

What is the most common age for a great author to publish their best work?

If you are not familiar with mean, also known as average, or median, we recommend that you learn about it in our lessons on average and median.

### Instructions

The histogram to the right displays the age of authors, at publication, for the top 100 novels from Le Monde’s survey. The red line is the mean age, and the yellow line is the median age.

Use the definition of mode below and the histogram to the right to guess where the mode falls. You will calculate the correct answer in the last exercise.

The mode is the most common observation in a dataset.

You will not be able to find the exact mode, because the histogram displays bins with a range of values. However, you can guess a range of values where you are most likely to see the mode.

script.py
```python
# Import packages
import codecademylib
import numpy as np
import pandas as pd

# Import matplotlib pyplot
from matplotlib import pyplot as plt

# Read in transactions data
greatest_books = pd.read_csv("top-hundred-books.csv")

# Save transaction times to a separate numpy array
author_ages = greatest_books['Ages']

# Use numpy to calculate the average age of the top 100 authors
average_age = np.mean(author_ages)
median_age = np.median(author_ages)

# Plot the figure
plt.hist(author_ages, range=(10, 80), bins=14,  edgecolor='black')
plt.title("Age of Top 100 Novel Authors at Publication")
plt.xlabel("Publication Age")
plt.ylabel("Count")
plt.axvline(average_age, color='r', linestyle='solid', linewidth=2, label="mean")
plt.axvline(median_age, color='y', linestyle='dotted', linewidth=3, label="median")
plt.legend()

plt.show()
```
