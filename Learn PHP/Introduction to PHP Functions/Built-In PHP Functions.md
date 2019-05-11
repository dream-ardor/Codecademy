## INTRO TO BUILT-IN PHP FUNCTIONS

## Review
In this lesson, you learned that built-in functions are functions provided by PHP. You learned about several specific built-in functions, how to understand a function’s description in the documentation, and how to discover new built-in functions.

We’ve only started to scratch the surface of all of the functions built into the PHP language. As you continue to learn PHP, you’ll come across many useful built-in functions. As you write your own code, if a task you’re performing feels tedious but common, check to see if there’s a built-in function to do it for you!

One final note: Throughout this lesson, you may have noticed that PHP’s built-in functions often don’t follow the function naming conventions we outlined. PHP’s built-in functions aren’t named following a single convention—some are snake-cased while others have unseparated words. It’s quirks like this that can make PHP a bit frustrating to learn. Be patient with yourself as you get comfortable with the built-in functions most useful to you, and don’t hesitate to look things up.

## Instructions
We’ve provided an example of each of the functions we’ve covered in this lesson. Play around with the code to make sure you understand how each one works, or try out some new built-in functions you discover!

```php
<?php
$string_var = "Check it out";
echo strtoupper($string_var) . "!\n";

echo ceil(8.873);
echo "\n";
  
echo pi();
echo "\n";

echo str_pad("PHP", 30, "*^*-", STR_PAD_BOTH);
echo "\n";

echo getrandmax();
echo "\n";

echo rand();
echo "\n";

echo rand(1, 52);
echo "\n";

echo abs(-1287);
echo "\n";

echo round(8723.999);
echo "\n";

echo substr_count($string_var, " ");
echo "\n";

echo strrev("\n.pu ti peeK .taerg gniod er'uoY");

echo strtolower("SOON, tHiS WILL Look NoRmAL.\n");

echo str_repeat("There's no place like home.\n", 3);

echo gettype($string_var);
echo "\n";
echo var_dump($string_var);
```
