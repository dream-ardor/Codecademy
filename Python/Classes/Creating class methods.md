Creating class methods<br>
Besides member variables, classes can also have their own methods. For example:

class Square(object):
  def __init__(self, side):
    self.side = side

  def perimeter(self):
    return self.side * 4
The perimeter() class method is identical to defining any other function, except that it is written inside of the Square class definition.

Just like when we defined __init__(), you need to provide self as the first argument of any class method.

**Instructions:**

Inside the Car class, add a method named display_car to Car that will reference the Car's member variables to return the string, "This is a [color] [model] with [mpg] MPG." You can use the str() function to turn your mpg into a string when creating the display string.

Replace the individual print statements with a single print command that displays the result of calling my_car.display_car()

**My Code:**
```python
class Car(object):
  condition = "new"
  def __init__(self, model, color, mpg):
    self.model = model
    self.color = color
    self.mpg   = mpg

my_car = Car("DeLorean", "silver", 88)

print my_car.model
print my_car.color
print my_car.mpg

```
