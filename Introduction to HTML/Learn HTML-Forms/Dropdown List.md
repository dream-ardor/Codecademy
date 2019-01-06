LEARN HTML: FORMS

Dropdown list

Radio buttons are great if we want our users to pick one option out of a few visible options, but imagine if we have a whole list of options! This situation could quickly lead to a lot of radio buttons to keep track of.

An alternative solution is to use a dropdown list to allow our users to choose one option from an organized list. Here's the code to create a dropdown menu:
```html
<form>
  <label for="lunch">What's for lunch?</label>
  <select id="lunch" name="lunch">
    <option value="pizza">Pizza</option>
    <option value="curry">Curry</option>
    <option value="salad">Salad</option>
    <option value="ramen">Ramen</option>
    <option value="tacos">Tacos</option>
  </select>
</form>
```
Which renders: rendered dropdown list with the first option showing

And if we click on the field containing the first option, the list is revealed: rendered dropdown list with the all options showing

Notice in the code that we're using the element <select> to create the dropdown list. To populate the dropdown list, we add multiple <option> elements, each with a value attribute. By default, only one of these options can be selected.

The text rendered is the text included between the opening and closing <option> tags. However, it is the value of the value attribute that is used in form submission. When the form is submitted, the information from this input field will be sent using the name of the select and the value of the chosen option. For instance, if a user selected Pizza from the dropdown list, the information would be sent as "lunch=pizza".

**Instructions:**
Let's now give our users a choice of buns using a dropdown list.

In section element with a class of "bun-type" there is a <label> that we can associate a <select> element with.

Add a <select> element with a name of "bun" and an id of "bun".

Inside the <select> element, add 3 <option>s.

The first <option> should have a value of "sesame" and display the text Sesame on the webpage.
The second <option> should have a value of "potato" and display the text Potato on the webpage.
The third <option> can be a value that you choose and display text relevant to the value (make sure it's not empty!)

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>Dropdown List</title>
  </head>
  <body>
    <section id="overlay">
      <img src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg" alt="Davie's Burgers Logo" id="logo">
      <hr>
      <form>
        <h1>Create a burger!</h1>
        <section class="protein">
          <label for="patty">What type of protein would you like?</label>
    			<input type="text" name="patty" id="patty">
        </section>
        <hr>
  <section class="patties">
          <label for="amount">How many patties would you like?</label>
          <input type="number" name="amount" id="amount">
        </section>
        <hr>
        <section class="cooked">
          <label for="doneness">How do you want your patty cooked</label>
          <br>
          <span>Rare</span>
          <input type="range" name="doneness" id="doneness" value="3" min="1" max="5">
          <span>Well-Done</span>
        </section>
        <hr>
        <section class="toppings">
          <span>What toppings would you like?</span>
          <br>
          <input type="checkbox" name="topping" id="lettuce" value="lettuce">
          <label for="lettuce">Lettuce</label>
          <input type="checkbox" name="topping" id="tomato" value="tomato">
          <label for="tomato">Tomato</label>
          <input type="checkbox" name="topping" id="onion" value="onion">
          <label for="onion">Onion</label>
        </section>
        <hr>
        <section class="cheesy">
          <span>Would you like to add cheese?</span>
          <br>
          <input type="radio" name="cheese" id="yes" value="yes">
          <label for="yes">Yes</label>
          <input type="radio" name="cheese" id="no" value="yes">
          <label for="no">No</label>
        </section>
        <hr>
        <section class="bun-type">
        <label for="bun">What type of bun would you like?</label>
          <!--Add your code below-->
          <select name="bun" id="bun">
            <option value="sesame">Sesame</option>
   <option value="potato">Potato</option>
  <option value="buttermilk">Buttermilk</option>
          </select>
          </section>
        </form>
    </section>
  </body>
</html>
```
