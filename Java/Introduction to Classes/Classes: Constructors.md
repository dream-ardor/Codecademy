## JAVA: INTRODUCTION TO CLASSES

### Classes: Constructors

We create instances with a constructor method defined within the class.

Here’s the Car class with a constructor:
```java
public class Car {
  public Car() {//constructor method starts

    // create Car instance

  }//constructor method ends

  public static void main(String[] args) {
    // program tasks
  }
}
```
The constructor, Car(), shares a name with the class.

We create instances by calling or invoking the constructor within main(). This example assigns an instance to the variable ferrari:
```java
public class Car {

  public Car() {
  }

  public static void main(String[] args) {
    /*
    invoke a constructor using 
    'new', the name, and parentheses:
    new Car()
    */
    Car ferrari = new Car(); 
  }
}
```
As with other variable declarations, we specify the type: Car, and name: ferrari. Variables that reference an instance have a type of the class name.

We invoke the constructor method: Car(), and use the keyword new to indicate that we’re creating an instance. Omitting new causes an error.

This is the first time we’ve called a method that we’ve also defined. main() is run automatically and we did not define the println() method.

Introducing a second method is a big step in your programming journey, congratulations!

### Instructions

Let’s explore how code execution moves around the file with two methods.

Add a print statement inside our Store constructor with the message: I am inside the constructor method.

We’ll see this message whenever we create an instance of Store by calling the constructor.

We did not see our constructor message printed because we haven’t run the code inside the constructor.

Inside main(), create an instance of Store called lemonadeStand. Don’t forget the new keyword!

We should see the constructor message.

Inside main(), print lemonadeStand to see how Java represents this instance.

Review the order of the printed messages:

* Running the program invokes main()
* We create an instance so we move from main() to Store()
* The code inside Store() runs
* When Store() finishes execution, we return to main()

## My Code
```java
public class Store {
  
  // new method: constructor!
  public Store() {
    System.out.println("I am inside the constructor method.");
    
  }
  
  // main method is where we create instances!
  public static void main(String[] args) {
    System.out.println("Start of the main method.");
    // create the instance below
 Store lemonadeStand = new Store();
    
   // print the instance below
    System.out.println(lemonadeStand);
  }
}
```


