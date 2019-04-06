## LEARN JAVA: METHODS

### Returns

Remember, variables can only exist in the scope that they were declared in.

We can use a value outside of the method it was created in if we return it from the method.

We return a value by using the keyword return:
```java
public int numberOfTires() {
   int tires = 4;
   return tires;
}
```
This method, called numberOfTires, returns 4. In past exercises, when creating new methods, we used the keyword void. Here, we are replacing void with int, to signify that the return type is an int.

The void keyword (which means “completely empty”) indicates to the method that no value is returned after calling that method.

Alternatively, we can use datatype keywords (such as int, char, etc.) to specify that a method should return a value of that type.
```java
public static void main(String[] args){
  Car myCar = new Car("red");
  int numTires = myCar.numberOfTires();
}
```
Within main(), we called the numberOfTires() method on myCar. Since the method returns an int value of 4, we store the value 4 in an integer variable called numTires. If we printed numTires, we would see 4.

### Instructions

We want to have a method that returns the price plus tax.

Define a method called getPriceWithTax() that is intended to return the price plus the tax. It should take in no parameters and return a double.

You can leave the body of the method empty for now. Note: the code will have an error until we return the correct type from the method, which we will do in the next step.

Inside the getPriceWithTax() method, create a double variable totalPrice that is equal to price + price * 0.08. 0.08 is the tax applied to the price.

Then, return totalPrice.

Inside of main(), set a double variable lemonadePrice to the value returned by lemonadeStand.getPriceWithTax().

Now, print out lemonadePrice.

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
    double totalPrice = price + price * 0.08;
    return totalPrice;
    
  }
  // main method
  public static void main(String[] args) {
    Store lemonadeStand = new Store("Lemonade", 3.75);
    double lemonadePrice = lemonadeStand.getPriceWithTax();
    System.out.println(lemonadePrice);
  }
}
```
