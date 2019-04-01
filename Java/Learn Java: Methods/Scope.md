## Scope

A method is a task that an object of a class performs.

We mark the domain of this task using curly braces: {, and }. Everything inside the curly braces is part of the task. This domain is called the scope of a method.

We can’t access variables that are declared inside a method in code that is outside the scope of that method.

Looking at the Car class again:
```java
class Car {
  String color;
  int milesDriven;

  public Car(String carColor) {
    color = carColor;
    milesDriven = 0;         
  }

  public void drive() {
     String message = "Miles driven: " + milesDriven;
     System.out.println(message);
  }

  public static void main(String[] args){
     Car myFastCar = new Car("red");
     myFastCar.drive();
  }
}
```
The variable message, which is declared and initialized inside of drive, cannot be used inside of main()! It only exists within the scope of the drive() method.

However, milesDriven, which is declared at the top of the class, can be used inside all methods in the class, since it is in the scope of the whole class.

### Instructions

Inside of the advertise() method, change the productType variable to the cookie variable, which is declared in the main() method. This should also result in the printout:

Selling cookies!
Right?

No! We got an error! The cookie variable cannot be accessed inside of the advertise method. The scope is wrong! Change it back to productType:
```java
String message = "Selling " + productType + "!";
```
Inside of the main() method, print the String message, which is declared in the advertise() method. This should print:

Selling Cookies!
Right?

Foiled again! The message variable only exists inside the scope of the advertise() method!

Delete the faulty print statement from the main() method.

## My Code
```java
public class Store {
  // instance fields
  String productType;
  
  // constructor method
  public Store(String product) {
    productType = product;
  }
  
  // advertise method
  public void advertise() {
    String message = "Selling " + productType + "!";
		System.out.println(message);
  }
  
  // main method
  public static void main(String[] args) {
    String cookie = "Cookies";
    Store cookieShop = new Store(cookie);
   
    cookieShop.advertise();
  }
}
```
