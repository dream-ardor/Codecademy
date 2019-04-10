## Escape Sequences

We use quotation marks to indicate the start and end of a string. The quotation marks tell the computer that we want everything inside them to be treated as a single piece of data. But how do we include quotation marks inside a string?

Consider the following string: "She said "hi" to the dog."

In the code above, the quotes around “hi” are intended to be part of the string, but the computer will actually see two strings "She said " and " to the dog." with hi in between. Since hi won’t be recognized as valid PHP it will result in an error:
```php
echo "She said "hi" to the dog."; //syntax error, unexpected 'hi' (T_STRING)
```
In order to indicate which quotation marks the computer should view as instructions vs which it should view as simply characters, PHP allows for escape sequences. An escape sequence usually consists of a backslash (\) immediately followed by another character.
```php
echo "She said \"hi\" to the dog."; // Prints: She said "hi" to the dog.
```
Quotation marks aren’t the only symbol requiring an escape sequence. When we print multiple strings, PHP will print them to the same line by default:
```php
echo "1. Go to gym";
echo "2. Cook dinner"; 
```
The code above will output 1. Go to gym2. Cook dinner. To print the second string on a new line, we can use the newline escape sequence (\n):
```php
echo "1. Go to gym";
echo "\n2. Cook dinner"; 
/* Prints
1. Go to gym
2. Cook dinner
*/
```
You don’t need to worry about other escape sequences yet, but if you’d like to see the full list you can find one in the PHP documentation.

Let’s practice!

### Instructions

Let’s make a to-do list for you. Use echo to print a string to the console in the following format: 1. [thing you have to do]. For example, here’s ours: 1. Teach PHP.

Let’s create a new echo statement for the next item on our to-do list.

By default, this second statement would print on the same line as the first… Start this second string with the escape sequence for a new line character. Next, continue the string in the same format as before: 2. [Another thing to do].

Let’s throw a third thing on the list. This time, let’s mix it up. Include something inside your string wrapped in double quotes. For example, here’s ours 3. Learn to have "fun".

## My Code
```php
<?php
// Write your code below:
echo "1. Have hot food";
echo "\n2. Order a burrito";
echo "\n3. Deliver a \"huge\" fresh burrito!";





  
  
  
  



```
