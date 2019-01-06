LEARN HTML: FORMS

Checkbox Input

So far the types of inputs we've allowed were all single choices. But, what if we presented multiple options to users and allow them to select any number of options? Sounds like we could use checkboxes! In a <form> we would use the <input> element and set type="checkbox". Examine the code used to create multiple checkboxes:
```html
<form>
  <p>Choose your pizza toppings:</p>
  <label for="cheese">Extra cheese</label>
  <input id="cheese" name="topping" type="checkbox" value="cheese">
  <br>
  <label for="pepperoni">Pepperoni</label>
  <input id="pepperoni" name="topping" type="checkbox" value="pepperoni">
  <br>
  <label for="anchovy">Anchovy</label>
  <input id="anchovy" name="topping" type="checkbox" value="anchovy">
</form>
```
Which renders: HTML form asking user to select pizza toppings and three topping selections as checkboxes

Notice in the example provided:

there are assigned values to the value attribute of the checkboxes. These values are not visible on the form itself, that's why it is important that we use an associated <label> to identify the checkbox.
each <input> has the same value for the name attribute. Using the same name for each checkbox groups the <input>s together. However, each <input> has a unique id to pair with a <label>.
Alright, time to use checkboxes in our code!

**Instructions:**
Time to add some toppings! In the <section> with class="toppings", there are two <label>s but no associated <input> elements. Add an <input> element associated with the first <label>.

The created <input> should have:

an id set to "lettuce".
a name attribute with a value of "topping".
a type set to "checkbox"
a value of "lettuce".

Add another <input> element and associate it with the second <label>.

The <input> element should have:

an id set to "tomato".
a type set to "checkbox".
a name attribute with a value of "topping".
a value of "tomato".

Two choices are good, but it would be better to have even more.

Add another <input type="checkbox"> and <label> pair. Assign the name of the <input> to "topping". You're free to decide the value and id but make sure that your new <label> and <input> are associated.

**My Code:**
```html
<!DOCTYPE html>
<html dir="ltr" lang="en">
<head>
	<meta charset="utf-8">
	<link href="style.css" rel="stylesheet" type="text/css">
	<link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
	<title>Checkbox Input</title>
</head>
<body>
	<section id="overlay">
		<img alt="Davie's Burgers Logo" id="logo" src="https://s3.amazonaws.com/codecademy-content/courses/web-101/unit-6/htmlcss1-img_burger-logo.svg">
		<hr>
		<form>
			<h1>Create a burger!</h1>
			<section class="protein">
				<label for="patty">What type of protein would you like?</label> <input id="patty" name="patty" type="text">
			</section>
			<hr>
			<section class="patties">
				<label for="amount">How many patties would you like?</label> <input id="amount" name="amount" type="number">
			</section>
			<hr>
			<section class="cooked">
				<label for="doneness">How do you want your patty cooked</label><br>
				<span>Rare</span> <input id="doneness" max="5" min="1" name="doneness" type="range" value="3"> <span>Well-Done</span>
			</section>
			<hr>
			<section class="toppings">
				<span>What toppings would you like?</span><br>
				<!--Add your code below for the first checkbox-->
				 <input id="lettuce" name="topping" type="checkbox" value="lettuce"> <label for="lettuce">Lettuce</label> <!--Add your code below for the second checkbox-->
				 <input id="tomato" name="topping" type="checkbox" value="tomato"> <label for="tomato">Tomato</label> <!--Add your code below for the third checkbox-->
				 <label for="onion">Onion</label> <input id="onion" name="topping" type="checkbox" value="onion"> 
         <label for="peppers">Peppers</label> <input id="peppers" name="peppers" type="checkbox" value="peppers">
			</section>
		</form>
	</section>
</body>
</html>
```
