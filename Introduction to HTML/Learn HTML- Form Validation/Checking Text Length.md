LEARN HTML: FORM VALIDATION

Checking Text Length

In the previous exercise, we were able to use min and max to set acceptable minimum and maximum values in a number field. But what about text fields? There are certainly cases where we wouldn't want our users typing more than a certain number of characters (think about the message cap for Twitter). We might even want to set a minimum number of characters. Conveniently, there are built-in HTML5 validations for these situations.

To set a minimum number of characters for a text field, we add the minlength attribute and a value to set a minimum value. Similarly, to set the maximum number of characters for a text field, we use the maxlength attribute and set a maximum value. Let's take a look at these attributes in code:
```html
<form action="/example.html" method="POST">
  <label for="summary">Summarize your fillings in less than 250 characters</label>
  <input id="summary" name="summary" type="type" minlength="5" maxlength="250" required>
  <input type="submit" value="Submit">
</form>
```
If a user tries to submit the <form> with less than the set minimum, this message appears:

prompt on a number field for user to length the input

And if a user tries to type in more than the maximum allowed number of characters, they don't get a warning message, but they can't type it in!

Let's add this validation to our form.

**Instructions:**
For the login <form>, we want our users to have usernames that are at least 3 characters and at most 15. Let's add this validation to our current form.

To the <input> with an id of "username", add the following attributes and values:

a minlength of "3".
a maxlength of "15".

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <title>Sign Up Page</title>
    <link rel="stylesheet" href="style.css" type="text/css">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
  </head>
  <body>
    <section class="overlay">
      <h1>Sign Up</h1>
      <p>Create an account:</p>
      <form action="submission.html" method="GET">
        <!--Add the minlength and maxlength attributes to the input fields-->
        <label for="username">Username:</label>
        <br>
        <input id="username" name="username" type="text" required minlength="3" maxlength="15">
        <br>
        <label for="pw">Password:</label>
        <br>
        <input id="pw" name="pw" type="password" required>
        <br>
        <input type="submit" value="Submit">
      </form>
    </section>
  </body>
</html>
```
