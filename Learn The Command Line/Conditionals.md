Conditionals<br>

When bash scripting, you can use conditionals to control which portions of the script run. Use if to start the conditional, followed by the condition in square brackets ([ ]). then begins the code that will run if the condition is met. else begins the code that will run if the condition is not met. Lastly, the conditional is closed with a backwards if, fi.

A complete conditional in a bash script uses the following syntax:
```bash
if [ $index -lt 5 ]
then
  echo $index
else
  echo 5
fi
```

Bash scripts use a specific list of operators for comparison. Here we used -lt which is "less than". The result of this conditional is that if $index is less than 5, it will print to the screen. If it is 5 or greater, "5" will be printed to the screen.

Here is the list of comparison operators you can use within bash scripts:

Equal: -eq
Not equal: -ne
Less than or equal: -le
Less than: -lt
Greater than or equal: -ge
Greater than: -gt
Is null: -z

**Instructions:**
We've added two different greetings and a variable to store how many times the user has been greeted before. If this variable is less than 1, we want to use first_greeting. Otherwise, we want to use later_greeting.

* Add a line setting up the if conditional. Use the -lt operator.

* Use echo to print $first_greeting if the conditional is met and $later_greeting otherwise. Be sure to close the if statement.

* Run the script in the terminal. Try adjusting the value of $greeting_occasion to test your if statement.

**My Code:**
```bash
#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_number=1

if [ $greeting_occasion -lt 1]
then
  echo $first_greeting
else
  echo $later_greeting
fi
```
