OBJECT-ORIENTED JAVA

Classes: Constructor Parameters

Perfect! By adding a class constructor and creating instance variables, we will soon be able to use the Dog class. However, the class constructor Dog is still empty. Let's modify this by adding parameters to the Dog constructor.

You can think of parameters like options at an ice cream store. You can choose to order a traditional ice cream cone, but other times you may want to specify the size of the cone or the flavor of the ice cream.

For the Dog class, we can specify the initial dog age by adding parameters to the class constructor.

Parameters allow data types to be created with specified attributes.
Let's add parameters to our Car class constructor:
```java
class Car {

    //Use instance variables to model our Car class after a real-life car
    int modelYear;

    public Car(int year) {

        modelYear = year;
    }
}
```
In the example above, we add the int parameter year to the Car constructor.

The value of modelYear will equal the int value that is specified when we first use this class constructor.

**Instructions:**
Add an int parameter called dogsAge in between the parentheses of the Dog() constructor.

Inside of the constructor block, set the instance variable age equal to the dogsAge parameter

**My Code:**
```java
class Dog {

int age;
public Dog(int dogsAge) {
  age = dogsAge;
  
}
	public static void main(String[] args) {
  
	}
}
```
