## MEDIAN

### Introduction

In this lesson, you will learn how to find the median of a dataset — a common measure of a dataset's center. Each of the next three exercises will cover the following topics:

* Manually finding the median of a dataset
* Using Python's NumPy library to find the median of a dataset
* Interpreting what it means for a dataset to have similar and different median and mean values

In the lesson, we will use a dataset of the 100 greatest novels, determined by a French literary magazine, Le Monde. From the dataset, you will use the median to answer the question:

When are great authors most likely to publish their best work?

If you are not familiar with mean, also known as average, we recommend that you learn about it in our lesson on average.

### Instructions

The histogram to the right displays the age of authors, at publication, for the top 100 novels. The red line represents the average value of this dataset.

You can think of the median as being the observation in your dataset that falls right in the middle.

Using this informal definition of the median and the graph to the right, see if you can determine whether the median of this dataset falls to the right or the left of the mean. We will show you the correct answer in the last exercise.

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
average_age = np.average(author_ages)


print("The average age of the 100 greatest authors, according to Le Monde is: " + str(average_age))

# Plot the figure
plt.hist(author_ages, range=(10, 80), bins=14,  edgecolor='black')
plt.title("Age of Top 100 Novel Authors at Publication")
plt.xlabel("Publication Age")
plt.ylabel("Count")
plt.axvline(average_age, color='r', linestyle='solid', linewidth=2, label="Mean")
plt.legend()

plt.show()
```
