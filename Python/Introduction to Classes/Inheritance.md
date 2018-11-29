INTRODUCTION TO CLASSES<br>
Inheritance<br>
Finally, let's create an Equilateral class that inherits from our Triangle class. (An equilateral triangle is a triangle whose angles are all 60˚, which also means that its three sides are equal in length.)

**Instructions:**
Create a class named Equilateral that inherits from Triangle.

Inside Equilateral, create a member variable named angle and set it equal to 60.

Create an __init__() function with only the parameter self, and set self.angle1, self.angle2, and self.angle3 equal to self.angle (since an equilateral triangle's angles will always be 60˚).

**My Code:**
```python
class Triangle(object):
  def __init__(self, angle1, angle2, angle3):
    self.angle1 = angle1
    self.angle2 = angle2
    self.angle3 = angle3
  number_of_sides = 3
  def check_angles(self):
    if (self.angle1 + self.angle2 + self.angle3 == 180):
      return True
    else:
      return False
 
my_triangle = Triangle(90,30,60)
print my_triangle.number_of_sides
print my_triangle.check_angles()

class Equilateral(Triangle):
  angle = 60
  def __init__(self):
    self.angle1 = self.angle
    self.angle2 = self.angle
    self.angle3 = self.angle
 ```
