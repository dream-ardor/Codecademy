LEARN HTML: FORMS

Range Input

Using an <input type="number"> is great if we want to allow users to type in any number of their choosing. But, if we wanted to limit what numbers our users could type we might consider using a different type value. Another option we could use is setting type to "range" which creates a slider.

To set the minimum and maximum values of the slider we assign values to the min and max attribute of the <input>. We could also control how smooth and fluid the slider works by assigning the step attribute a value. Smaller step values will make the slider more fluidly, whereas larger step values will make the slider move more noticeably. Take a look at the code to create a slider:
```html
<form>
  <label for="volume"> Volume Control</label>
  <input id="volume" name="volume" type="range" min="0" max="100" step="1">
</form>
```
The code above renders: rendered slider for volume control

In the example above, every time the slider moves by one, the value of the <input>'s value attribute changes.

**Instructions:**
Let's give our users an option for how they want to cook their patties. We can do this by adding a slider to the existing form.

In the section with class="cooked", add an <input> element. Set the id and name to "doneness". Also, set the type attribute to "range".

Since our form is getting long, you might have to scroll down to find the provided section.

For the newly created <input> set the:

min attribute to "0".
max attribute to "5".
step attribute to "0.5".

**My Code:**
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" type="text/css" href="style.css">
    <link href="https://fonts.googleapis.com/css?family=Rubik" rel="stylesheet">
    <title>Range Input</title>
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
		       <!--Add your code below-->
<input id="doneness" name="doneness" type="range" min="0" max="5" step="0.5"> 
          <span>Well-Done</span>
        </section>
        
      </form>
    </section>
  </body>
</html>
```
