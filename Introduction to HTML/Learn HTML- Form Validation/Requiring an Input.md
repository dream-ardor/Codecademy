LEARN HTML: FORM VALIDATION

Requiring an Input

Sometimes we have fields in our <form>s which are not optional, i.e. there must be information provided before we can submit it. To enforce this rule, we can add the required attribute to an <input> element. Take for example:
```html
<form action="/example.html" method="POST">
  <label for="allergies">Do you have any dietary restrictions?</label>
  <br>
  <input id="allergies" name="allergies" type="text" required>
  <br>
  <input type="submit" value="Submit">
</form>
```
This renders a text box, and if we try to submit the <form> without filling it out we get this message:

message pop up prompting user to fill in the field

The styling of the message varies from browser to browser, the picture above depicts the message in a Chrome browser. We'll also continue to show these messages as they appear in Chrome in later exercises.

Let's see how it shows up in your browser!

**Instructions:**
Currently, in the provided form, our users can submit it without putting any values inside the input field! What kind of guessing game is this??

Let's change that by adding a required attribute to the existing <input>.

After you clear this checkpoint, try submitting the form without filling out the fields.

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
        <!--Add a required attribute to the input element-->
        <label for="guess">Enter a number between 1-10:</label>
        <br>
        <input type="number" name="guess" id="guess" required>
        <br>
        <input type="submit" id="submission" value="Submit">
      </form>
    </section>
  </body>
</html>

```
