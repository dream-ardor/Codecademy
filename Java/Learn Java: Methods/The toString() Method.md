## LEARN JAVA: METHODS

### The toString() Method

When we print out Objects, we often see a String that is not very helpful in determining what the Object represents. In the last lesson, we saw that when we printed our Store objects, we would see output like:
```
Store@6bc7c054
```
where Store is the name of the object and 6bc7c054 is its position in memory.

This doesn’t tell us anything about what the Store sells, the price, or the other instance fields we’ve defined. We can add a method to our classes that makes this printout more descriptive.

When we define a toString() method for a class, we can return a String that will print when we print the object:
```java
class Car {

    String color;

    public Car(String carColor) {
        color = carColor;
    }

    public static void main(String[] args){
        Car myCar = new Car("red");
        System.out.println(myCar);
    }

   public String toString(){
       return "This is a " + color + " car!";
   }
}
```
When this runs, the command System.out.println(myCar) will print This is a red car!, which tells us about the Object myCar.

### Instructions

In the main() method, print the Objects lemonadeStand and cookieShop. Are these printouts helpful in understanding these Objects?

Create a toString() method for the Store class. The method signature should say that it is public, and that it returns a String. It shouldn’t take in any parameters. For now, have it return the String "Store".

"Store" isn’t very helpful! What kind of Store is it?

Change the toString() to return a String that describes this Store object.

Your String should look like:

This store sells productType at a price of price.

where productType and price are the values in those instance fields. For example, if it was a hat store where hats cost 8, the String would say:

This store sells hats at a price of 8.

Look at the printouts again. Are they more helpful now?

## My Code
```java
public class Store {
  // instance fields
  String productType;
  double price;
  
  // constructor method
  public Store(String product, double initialPrice) {
    productType = product;
    price = initialPrice;
  }
  
  // increase price method
  public void increasePrice(double priceToAdd){
    double newPrice = price + priceToAdd;
    price = newPrice;
  }
  
  // get price with tax method
  public double getPriceWithTax(){
    double tax = 0.08;
    double totalPrice = price + price*tax;
    return totalPrice;
  }
  
  public String toString(){
    return "This store sells " + productType + " at a price of " + price + ".";
    
  };

  // main method
  public static void main(String[] args) {
    Store lemonadeStand = new Store("Lemonade", 3.75);
    Store cookieShop = new Store("Cookies", 5);
    System.out.println(lemonadeStand);
    System.out.println(cookieShop);
    

  }
}
```
