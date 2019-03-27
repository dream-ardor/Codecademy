## JAVA: INTRODUCTION TO CLASSES

### Classes: Multiple Fields

Objects are not limited to a single instance field. We can declare as many fields as are necessary for the requirements of our program.

Let’s change Car instances so they have multiple fields.

We’ll add a boolean isRunning, that indicates the car engine is on and an int velocity, that indicates the speed at which the car is traveling.
```java
public class Car {
  String color;
  // new fields!
  boolean isRunning;
  int velocity;

  // new parameters that correspond to the new fields
  public Car(String carColor, boolean carRunning, int milesPerHour) {
    color = carColor;
    // assign new parameters to the new fields
    isRunning = carRunning;
    velocity = milesPerHour;
  }

  public static void main(String[] args) {
    // new values passed into the method call
    Car ferrari = new Car("red", true, 27);
    Car renault = new Car("blue", false, 70);

    renault.isRunning;
    // false
    ferrari.velocity;
    // 27
  }
}
```
The constructor now has multiple parameters to receive values for the new fields. We still specify the type as well as the name for each parameter.

Ordering matters! We must pass values into the constructor invocation in the same order that they’re listed in the parameters.
```java
// values match types, no error
Car honda = new Car("green", false, 0);

// values do not match types, error!
Car junker = new Car(true, 42, "brown");
```
### Instructions

Add two new instance fields for Store.

inventoryCount of type int. inventoryPrice of type double.

Update the Store constructor method with the new parameters.

The parameters should be product, count, and price, in that order.

You must use that order and include the types for each parameter.

For example, product is of type String because that value is assigned to the instance field String productType.

In the body of the Store constructor, assign the parameter values to the appropriate instance fields.

Inside main(), create an instance of Store called cookieShop.

## My Code
```java
public class Store {
  // instance fields
  String productType;
  int inventoryCount;
  double inventoryPrice;
  
  
  // constructor method
  public Store(String product, int count, double price) {
    
    productType = product;
    inventoryCount = count;
    inventoryPrice = price;
    
  }
  
  // main method
  public static void main(String[] args) {
    Store cookieShop = new Store("cookies",12,3.75);
    
  }
}
```

cookieShop has "cookies" as the product.

cookieShop has 12 cookies to sell and each cookie costs 3.75.
