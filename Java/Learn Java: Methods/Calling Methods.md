## Calling Methods

Great! When we add the startEngine() method to the Car class, it becomes available to use on any Car object. We can do this by calling the method on the Car object we created, for example.

Here is an example of calling a method on an object using the Car class:
```java
class Car {

  String color;

  public Car(String carColor) {
    color = carColor;
  }

  public void startEngine() {
    System.out.println("Starting the car!");
    System.out.println("Vroom!");
  }

  public static void main(String[] args){
    Car myFastCar = new Car("red");
    myFastCar.startEngine();
  }
}
```
In the example above, we call the startEngine() method on the myFastCar object. This method call occurs inside the main() method. Running the program results in printing Vroom! to the output terminal.

## Instructions

Last exercise, we defined a new method, advertise(), but we didn’t actually see it run.

We now have a Store class with advertise() defined.

Call the advertise() method on the lemonadeStand object in the main() method and see what the output is!

Now, call the advertise() method on the lemonadeStand object two more times. It should be called in the main() method three times total.

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
		System.out.println("Selling " + productType + "!");
    System.out.println("Come spend some money!");
  }
  
  // main method
  public static void main(String[] args) {
    Store lemonadeStand = new Store("Lemonade");
    lemonadeStand.advertise();
    lemonadeStand.advertise();
    lemonadeStand.advertise();
  }
}
```
