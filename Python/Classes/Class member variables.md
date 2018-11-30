Class member variables<br>
Classes can have member variables that store information about each class object. We call them member variables since they are information that belongs to the class object.

Creating member variables and assigning them initial values is as easy as creating any other variable:

class ClassName(object):
  memberVariable = "initialValue"
  
**Instructions:**
Inside your Car class, replace the pass statement with a new member variable named condition and give it an initial value of the string "new".

**My Code:**
```python
class Car(object):
  condition = "new"

my_car = Car()
```
