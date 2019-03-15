## MODE

### Mode

The formal definition for the mode of a dataset is:

The most frequently occurring observation in the dataset. A dataset can have multiple modes if there is more than one value with the same maximum frequency.

While you may be able to find the mode of a small dataset by simply looking through it, if you have trouble, we recommend you follow these two steps:

Find the frequency of every unique number in the dataset
Determine which number has the highest frequency

Example

Say we have a dataset with the following ten numbers:

24, 16, 12, 10, 12, 28, 38, 12, 28, 24

Let’s find the frequency of each number:

24	16	12	10	28	38
2	1	3	1	2	1

From the table, we can see that our mode is 12, the most frequent number in our dataset.

### Instructions

Determine the mode of the ages for the first ten authors in the Le Monde survey:

29, 49, 42, 43, 32, 38, 37, 41, 27, 27

Save the value to mode_age.

Determine the number of authors who were the age of the mode. Save the number to mode_count.

## My Code
```python
import numpy as np

# Set first_ten_authors equal to their ages
first_ten_authors = np.array([29, 49, 42, 43, 32, 38, 37, 41, 27, 27])

# Save the mode value to mode_age
mode_age = 27

# Save the count of authors with the mode age
mode_count = 2

# Print the sorted array and median value
print("The ages of the first ten authors is: " + str(first_ten_authors))
print("The mode of the first ten authors is: " + str(mode_age))
print("The number of authors who were " + str(mode_age) + " when their book was published is " + str(mode_count))
```
