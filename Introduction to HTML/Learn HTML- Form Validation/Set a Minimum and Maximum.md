LEARN HTML: FORM VALIDATION

Set a Minumum and Maximum

Another built-in validation we can use is to assign a minimum or maximum value for a number field, e.g. <input type="number"> and <input type="range">. To set a minimum acceptable value, we use the min attribute and assign a value. On the flip side, to set a maximum acceptable value, we assign the max attribute a value. Let's see this in code:
```html
<form action="/example.html" method="POST">
  <label for="guests">Enter # of guests:</label>
  <input id="guests" name="guests" type="number" min="1" max="4">
  <input type="submit" value="Submit">
</form>
```
If a user tries to submit an input that is less than 1 a warning will appear: prompt on a number field for user to input a value greater than or equal to 1

A similar message will appear if a user tries to input a number greater than 4. Let's now see this action.

**Instructions:**
Time to enforce the rules of the guessing game.

In the opening <input> tag, set the min attribute to "1" and the max value to "10".

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Number Guessing</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Spicy+Rice" rel="stylesheet">
  </head>
  <body>
    <section class="overlay">
      <h1>Guess the right number!</h1>
      <form action="check.html" method="GET">
        <label for="guess">Enter a number between 1-10:</label>
        <br>
        <!--Add the min and max attribute to the input-->
        <input type="number" name="guess" id="guess" required min="1" max="10">
        <br>
        <input type="submit" id="submission" value="Submit">
      </form>
    </section>
  </body>
</html>
```
