LEARN PYTHON: SYNTAX

Errors

Humans are prone to making mistakes. Humans are also typically in charge of creating computer programs. To compensate, programming languages attempt to understand and explain mistakes made in their programs.

Python refers to these mistakes as errors and will point to the location where an error occurred with a ^ character. When programs throw errors that we didn't expect to encounter we call those errors bugs. Programmers call the process of updating the program so that it no longer produces unexpected errors debugging.

Two common errors that we encounter while writing Python are SyntaxError and NameError.

SyntaxError means there is something wrong with the way your program is written — punctuation that does not belong, a command where it is not expected, or a missing parenthesis can all trigger a SyntaxError.

A NameError occurs when the Python interpreter sees a word it does not recognize. Code that contains something that looks like a variable but was never defined will throw a NameError.

**Instructions:**
You might encounter a SyntaxError if you open a string with double quotes and end it with a single quote. Update the string so that it starts and ends with the same punctuation.

You might encounter a NameError if you try to print a single word string but fail to put any quotes around it. Python expects the word of your string to be defined elsewhere but can't find where it's defined. Add quotes to either side of the string to squash this bug.

Update the malformed strings in the workspace to all be strings.

**My Code:**
```py
print("This message has mismatched quote marks!")
print("Abracadabra")
```
