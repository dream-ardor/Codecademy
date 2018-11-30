Initializing a class<br>
There is a special function named __init__() that gets called whenever we create a new instance of a class. It exists by default, even though we don't see it. However, we can define our own __init__() function inside the class, overwriting the default version. We might want to do this in order to provide more input variables, just like we would with any other function.

The first argument passed to __init__() must always be the keyword self - this is how the object keeps track of itself internally - but we can pass additional variables after that.

In order to assign a variable to the class (creating a member variable), we use dot notation. For instance, if we passed newVariable into our class, inside the __init__() function we would say:

self.new_variable = new_variable

**Instructions:**
Define the __init__() function of the Car class to take four inputs: self, model, color, and mpg. Assign the last three inputs to member variables of the same name by using the self keyword.

**My Code:**
```python
class Car(object):
  condition = "new"
  def __init__(self,model,color,mpg):
    self.model = model
    self.color = color
    self.mpg = mpg

my_car = Car("DeLorean","silver",88)
```
