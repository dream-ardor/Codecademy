Overriding methods<br>
Since our ElectricCar is a more specialized type of Car, we can give the ElectricCar its own drive_car() method that has different functionality than the original Car class's.

**Instructions:**
Inside ElectricCar add a new method drive_car that changes the car's condition to the string "like new".

Then, outside of ElectricCar, print the condition of my_car

Next, drive my_car by calling the drive_car function

Finally, print the condition of my_car again

**My Code:**
```python
class Car(object):
  condition = "new"
  def __init__(self, model, color, mpg):
    self.model = model
    self.color = color
    self.mpg   = mpg
  
  def display_car(self):
    return "This is a " + self.color + " " + self.model + " with " + str(self.mpg) + " MPG."
  
  def drive_car(self):
    self.condition = "used"

my_car = Car("DeLorean", "silver", 88)

class ElectricCar(Car):
  def __init__(self,battery_type, model, color, mpg):
    self.battery_type = battery_type
    self.model = model
    self.color = color
    self.mpg = mpg
    
  def drive_car(self):
    self.condition = "like new"
    
my_car = ElectricCar("molten salt", "Mazda", "white", 30)

print my_car.battery_type
print my_car.model
print my_car.color
print my_car.mpg

print my_car.condition
my_car.drive_car()
print my_car.condition
```
