## MEAN

### Calculating Mean

The mean, often referred to as the average, is a way to measure the center of a dataset.

The average of a set is calculated using a two-step process:

Add all of the observations in your dataset.

Divide the total sum from step one by the number of points in your dataset.

The equation above is used to calculate mean. x1, x2, ... xn are observations from a dataset of n observations.

Example

Imagine that we wanted to calculate average of a dataset with the following four observations:
```python
data = [4, 6, 2, 8]

Step One: Calculate the total
4 + 6 + 2 + 8 = 20 4+6+2+8=20

Step Two: Divide by the number of observations
The total is equal to 20, and the number of observations is equal to 4.

```
The average of this dataset is equal to 5.

### Instructions

In this exercise, you will use Python to find the average age of the first four authors in Le Monde's top 100 books.

29, 49, 42, 43

Add the values together, and set total equal to the answer.

Divide total by the number of values in the dataset, and set mean_value to the answer.

Take a look at the result in the terminal. Keep that number in your head as you progress through the lesson.

## My Code
```python
# Set total equal to the sum
total = 29 + 49 + 42 + 43

# Set mean_value equal to the mean
mean_value = total / 4

# The following code prints the total and mean
print("The sum total is equal to: " + str(total))
print("The mean value is equal to: " + str(mean_value))
```
