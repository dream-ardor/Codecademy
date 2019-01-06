LEARN HTML: FORMS

Radio Button Input

Checkboxes work well if we want to present users with multiple options and let them choose one or more of the options. However, there are cases where we want to present multiple options and only allow for one selection — like asking users if they agree or disagree with the terms and conditions. Let's look over the code used to create radio buttons:
```html
<form>
  <p>What is sum of 1 + 1?</p>
  <input type="radio" id="two" name="two" value="2">
  <label for="two">2</label>
  <br>
  <input type="radio" id="eleven" name="eleven" value="11">
  <label for="eleven">11</label>
</form>
```
Which renders:

rendered form containing radio buttons

Notice from the code snippet, radio buttons (like checkboxes) do not display their value. We have an associated <label> to represent the value of the radio button. To group radio buttons together, we assign them the same name and only one radio button from that group can be selected.

Let's see this in action by creating our own radio buttons.

**Instructions:**
We can give our users the option to make the burger into a cheeseburger. Let's use radio buttons for that.

In section element with a class of "cheesy" there are two <label>s that don't have associated <input> elements. Add an <input> element associated with the first <label>.

The created <input> should have:

an id set to "yes".
a type set to "radio"
a name attribute with a value of "cheese".
a value of "yes".

Awesome, now add another <input> element to give users another choice. The created <input> should have:

an id set to "no".
a type set to "radio"
a name attribute with a value of "cheese".
a value of "no". 

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>Radio Input</title>
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
	        <!--Add your first radio button below-->
<input id="yes" type="radio" name="cheese" value="yes">
          <label for="yes">Yes</label>
	        <!--Add your second radio button below-->
<input id="no" type="radio" name="cheese" value="no">    

          <label for="no">No</label>
        </section>
        
      </form>
    </section>
  </body>
</html>
```
