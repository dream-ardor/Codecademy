## Review

Awesome work! We’ve covered a lot of material in this lesson, so let’s review:

* Strings are collections of text that the computer treats as a single piece of data.
* A string can be any length and contain any letters, numbers, symbols, or spaces surrounded by quotation marks.
* In order to include certain characters inside strings we have to use escape sequences.
* An operator is a character that performs a task in our code.
* We can use the concatenation operator (.) to combine two strings into one.
* Variables are a fundamental programming concept which allow us to easily reuse data in our code.
* We declare a variable using the dollar sign ($) followed by the variable name and then use the assignment operator (=) to give it a value.
* PHP has variable parsing which allows us to include variables directly in our strings.
* Once a variable has been assigned, we can change its value. This is called reassignment.
* We can create an alias for a variable, instead of just a copy, using the reference assignment operator (=&).
* Operations to the right of the assignment operator will be evaluated before assignment takes place.
* The concatenating assignment operator (.=) is a shorthand notation for reassigning a string variable to its current value appended with another string value.

If that was a lot to take in, don’t worry about memorizing everything right away. Remember that when you want to explore more about the language, the documentation is a great place to get comfortable exploring.

```php
<?php
	echo "Hello, Learner!";

	echo "\nWe hope you enjoyed this lesson.";
    
  echo "\nAre you excited?" . "\nTo learn more?";
    
  $favorite_language = "PHP";

  $message = "$favorite_language is by far our favorite language.";

  $message .= " It's yours now too, right?";
    
  echo "\n" . $message . " Right?!";  
```
```
Hello, Learner!
We hope you enjoyed this lesson.
Are you excited?
To learn more?
PHP is by far our favorite language. It's yours now too, right? Right?! 
```
