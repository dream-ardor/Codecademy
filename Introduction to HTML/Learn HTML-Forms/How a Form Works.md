LEARN HTML: FORMS

How a Form Works

We can think of the internet as a network of computers which send and receive information. Computers need an HTTP request to know how to communicate. The HTTP request instructs the receiving computer how to handle the incoming information. More information can be found in our article about HTTP requests.

The <form> element is a great tool for collecting information, but then we need to send that information somewhere else for processing. We need to supply the <form> element with both the location of where the <form>'s information goes and what HTTP request to make. Take a look at the sample <form> below:
```html
<form action="/example.html" method="POST">
</form>
```
In the above example, we've created the skeleton for a <form> that will send information to example.html as a POST request — the action attribute determines where the information is sent and the method attribute is assigned a HTTP verb that is included in the HTTP request. (Note: HTTP verbs like POST do not need to be capitalized for the request to work, but it's done so out of convention. In the example above we could have written method="post" and it would still work)

The <form> element can also contain child elements. For instance, it would be helpful to provide a header so that users know what this <form> is about. We could also add a paragraph to provide even more detail. Let's see an example of this in code:
```html
<form action="/example.html" method="POST">
  <h1>Creating a form</h1>
  <p>Looks like you want to learn how to create an HTML form. Well, the best way to learn is to play around with it.</p>
</form>
```
The example above doesn't collect any user input, but we'll do that in the next exercise. For now, let's practice making the foundation of an HTML <form>!

**Instructions:**
* In the section element, add a <form> element under the provided comment. Assign the <form> an action attribute with a value of "/practice.html" and a method attribute with a value of "POST".

* Right now we have a blank <form> on a burger site, let's add some context.

* Add an h1 inside the form element with text related to the site between the opening and closing h1 tags.

* Add some details to the form by inserting a <p> element below the h1 element. Write a relevant description within the <p> element.

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>HTML Forms</title>
  </head>
  <body>
    <section id="overlay">
      <img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">
      <hr>
      <!--Add your code below-->
      <form action="/practice.html" method="POST">
      <h1>Welcome to Davie's Burgers! </h1>
        <p>We have the hottest and biggest meats in town!</p>
        
        </form>
      
    </section>
  </body>
</html>
```
