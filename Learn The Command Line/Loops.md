Loops<br>
There are 3 different ways to loop within a bash script: for, while and until.

A for loop is used to iterate through a list and execute an action at each step. For example, if we had a list of words stored in a variable paragraph, we could use the following syntax to print each one:
```
for word in $paragraph
do
  echo $word
done
```
Note that word is being "defined" at the top of the loop so there is no $ prepended. Remember that we prepend the $ when accessing the value of the variable. So, when accessing the variable within the do block, we use $word as usual.

Within bash scripting until and while are very similar. while loops keep looping while the provided condition is true whereas until loops loop until the condition is true. Conditions are established the same way as they are within an if block, between square brackets. If we want to print the index variable as long as it is less than 5, we would use the following while loop:
```
while [ $index -lt 5 ]
do
  echo $index
  index=$((index + 1))
done
```
Note that arithmetic in bash scripting uses the $((...)) syntax and within the brackets the variable name is not prepended with a $.

The same loop could also be written as an until loop as follows:
```
until [ $index -eq 5 ]
do
  echo $index
  index=$((index + 1))
done
```
**Instructions:**
* Start by opening a while loop directly after the greeting_occasion variable. We want to loop while $greeting_occasion is less than 3.

* Move the existing if...fi block inside of the while loop. Remember to use the do and done keywords. Increment greeting_occasion on each loop.

* Run the script. You should see the first greeting as "Nice to meet you!" followed by two "How are you?" greetings.

**Solution:**
```bash
#!/bin/bash
first_greeting="Nice to meet you!"
later_greeting="How are you?"
greeting_occasion=0
while [ $greeting_occasion -lt 3 ]
do
  if [ $greeting_occasion -lt 1 ]
  then
    echo $first_greeting
  else
    echo $later_greeting
  fi
  greeting_occasion=$((greeting_occasion + 1))
done
```
