LEARN HTML: FORMS

Password Input

Think about all those times we have to put sensitive information, like a password or PIN, into a <form>. We wouldn't want our information to be seen by anyone peeking over our shoulder! Luckily, we have the type="password" attribute for <input>!

An <input type ="password"> element will replace input text with another character like an asterisk (*) or a dot (•). The code below provides an example of how to create a password field:
```html
<form>
  <label for="user-password">Password: </label>
  <input type="password" id="user-password" name="user-password">
</form>
```
After a user types into the field, it would look like:

password field in a form with 6 dots showing text added to the field
Even though the password field obscures the text of the password, when the form is submitted, the value of the text is sent. In other words, if "hunter2" is typed into the password field, "user-password=hunter2" is sent along with the other information on the form.

**Instructions:**
To complete our login page in index.html we need a password field. Add an <input> element under the second <label> element.

* Assign the id to the correct value to associate the second <label> with this new <input>.
* Set the newly created <input> element's type attribute to "password".
* Set the name attribute to "user-pw".

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>Password Input</title>
  </head>
  <body>
    <section id="overlay">
      <img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">
      <hr>
      <form>
				<h1>Login to start creating a burger!</h1>
        <label for="username">Username:</label>
  			<input type="text" name="username" id="username">
        <br>
        <label for="user-pw">Password:</label>
        <!--Add your code below-->
        <input id="user-pw" type="password" name="user-pw">
      </form>
    </section>
  </body>
</html>
```
