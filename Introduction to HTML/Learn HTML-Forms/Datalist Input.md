LEARN HTML: FORMS

Datalist Input

Even if we have an organized dropdown list, if the list has a lot of options, it could be tedious for users to scroll through the entire list to locate one option. That's where using the <datalist> element comes in handy.

The <datalist> is used with an <input type="text"> element. The <input> creates a text field that users can type into and filter options from the <datalist>. Let's go over a concrete example:
```html
<form>
  <label for="city">Ideal city to visit?</label>
  <input type="text" list="cities" id="city" name="city" />

  <datalist id="cities">
    <option value="New York City"></option>
    <option value="Tokyo"></option>
    <option value="Barcelona"></option>
    <option value="Mexico City"></option>
    <option value="Melbourne"></option>
    <option value="Other"></option>  
  </datalist>
</form>
```
Notice, in the code above, we have an <input> that has a list attribute. The <input> is associated to the <datalist> via the <input>'s list attribute and the id of the <datalist>.

From the code provided, the following form is rendered: input field with a label 'Ideal city to visit?'

And when field is selected: clicking on the input field reveals a dropdown 
list

While <select> and <datalist> share some similarities, there are some major differences. In the associated <input> element, users can type in the input field to search for a particular option. If none of the <option>s match, the user can still use what they typed in. When the form is submitted, the value of the <input>'s name and the value of the option selected, or what the user typed in, is sent as a pair.

Now it's time to make a <datalist> of our own!

**Instructions:**
Time to add some sauce! Users might get creative with what sauce they choose to put, so let's use the <datalist> element.

In section element with a class of "sauce-selection", we already have the <label> and <input> set up. Add a <datalist> element with an id of "sauces".

Inside the <datalist> element, add 3 <option>s.

The first <option> should have a value of "ketchup".
The second <option> should have a value of "mayo".
The third <option> can be a value that you choose and display text relevant to the value (make sure it's not empty!)

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
    			<input type="text" name="patty" id="patty" value="beef">
        </section>
        <hr>
        <section class="patties">
          <label for="amount">How many patties would you like?</label>
          <input type="number" name="amount" value="2" id="amount">
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
          <select name="bun" id="bun">
            <option value="sesame">Sesame</option>
            <option value="potato">Potato</option>
            <option value="pretzel">Pretzel</option>
          </select>
        </section>
        <hr>

        <section class="sauce-selection">
					<label for="sauce">What type of sauce would you like?</label>
          <input list="sauces" id="sauce" name="sauce">
          <!--Add your code below-->
          <datalist id="sauces">
            <option value="ketchup">Ketchup</option>
            <option value="mayo">Mayo</option>
            <option value="bbq sauce">BBQ Sauce</option>
          </datalist>
          
        </section>

      </form>
    </section>
  </body>
</html>
```
