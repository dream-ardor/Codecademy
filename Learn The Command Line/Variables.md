Variables<br>
Within bash scripts (or the terminal for that matter), variables are declared by simply setting the variable name equal to another value. For example, to set the variable greeting to "Hello", you would use the following syntax:
```bash
greeting="Hello"
```
Note that there is no space between the variable name, the equals sign, or "Hello".

To access the value of a variable, we use the variable name prepended with a dollar sign ($). In the previous example, if we want to print the variable value to the screen, we use the following syntax:
```bash
echo $greeting
```
**Instructions:**
* Create a variable phrase on the line before the current echo statement. Set the phrase equal to the string "Hello to you!".
* Update the echo statement to make use of the variable instead of the fixed string.
* Run the script in the terminal.

**My Code:**
```bash
#!/bin/bash
phrase="Hello to you!"
echo $phrase
```
