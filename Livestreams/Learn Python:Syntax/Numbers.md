LEARN PYTHON: SYNTAX

Numbers

Computers can understand much more than just strings of text. Python has a few numeric data types. It has multiple ways of storing numbers. Which one you use depends on your intended purpose for the number you are saving.

An integer, or int, is a whole number. It has no decimal point and contains all counting numbers (1, 2, 3, ...) as well as their negative counterparts and the number 0. If you were counting the number of people in a room, the number of jellybeans in a jar, or the number of keys on a keyboard you would likely use an integer.

A floating-point number, or a float, is a decimal number. It can be used to represent fractional quantities as well as precise measurements. If you were measuring the length of your bedroom wall, calculating the average test score of a seventh-grade class, or storing a baseball player's batting average for the 1998 season you would likely use a float.

Numbers can be assigned to variables or used literally in a program:
```py
an_int = 2
a_float = 2.1

print(an_int + 3)
# prints 5
```
Above we defined an integer and a float as the variables an_int and a_float. We printed out the sum of the variable an_int with the number 3. We call the number 3 here a literal, meaning it's actually the number 3 and not a variable with the number 3 assigned to it.

Floating-point numbers can behave in some unexpected ways due to how computers store them. For more information on floating-point numbers and Python, review Python's documentation on floating-point limitations.

**Instructions:**
A recent movie-going experience has you excited to publish a review. You rush out of the cinema and hastily begin programming to create your movie-review website: The Big Screen's Greatest Scenes Decided By A Machine.

Create the following variables and assign integer numbers to them: release_year and runtime.

Now, create the variable rating_out_of_10 and assign it a float number between one and ten.

**My Code:**
```py
# Define the release and runtime integer variables below:
release_year = 2019
runtime = 2


# Define the rating_out_of_10 float variable below: 
rating_out_of_10 = 6.9
```
