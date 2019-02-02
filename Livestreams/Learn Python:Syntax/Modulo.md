LEARN PYTHON: SYNTAX

Modulo

Python offers a companion to the division operator called the modulo operator. The modulo operator is indicated by % and gives the remainder of a division calculation. If the number is divisible, then the result of the modulo operator will be 0.
```py
# Prints 4 because 29 / 5 is 5 with a remainder of 4
print(29 % 5)

# Prints 2 because 32 / 3 is 10 with a remainder of 2
print(32 % 3)

# Modulo by 2 returns 0 for even numbers and 1 for odd numbers
# Prints 0
print(44 % 2)
```
Here, we use the modulo operator to find the remainder of division operations. We see that 29 % 5 equals 4, 32 % 3 equals 2, and 44 % 2 equals 0.

The modulo operator is useful in programming when we want to perform an action every nth-time the code is run. Can the result of a modulo operation be larger than the divisor? Why or why not?

**Instructions:**

You're trying to divide a group into four teams. All of you count off, and you get number 27.

Find out your team by computing 27 modulo 4. Save the value to my_team.


Print out my_team. What number team are you on?

Food for thought: what number team are the two people next to you (26 and 28) on? What are the numbers for all 4 teams?

**My Code:**
```py
my_team = 27 % 4
print(my_team)

team_a = 26 % 4
print(team_a)

team_b = 28 % 4
print(team_b)
```
