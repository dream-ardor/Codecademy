OBJECT-ORIENTED JAVA

Generalizations

Great work! Let's review everything that we've learned about object-oriented programming in Java so far.

* Class: a blueprint for how a data structure should function

* Constructor: instructs the class to set up the initial state of an object

* Object: instance of a class that stores the state of a class

* Method: set of instructions that can be called on an object

* Parameter: values that can be specified when creating an object or calling a method

* Return value: specifies the data type that a method will return after it runs

* Inheritance: allows one class to use functionality defined in another class

**Instructions:**
Inside of the main method, create a new Coffee object called myOrder.

On the next line, call the addSugar method on myOrder and specify 2 as the argument.

Modify the Coffee class so that it inherits from the Beverage class.

Inside of main, call the isFull method on the myOrder object.

**My Code:**
```java
class Coffee extends Beverage {
	
	public Coffee() {

	}
	
	public void addSugar(int cubes) {

		System.out.println("You added " + cubes + " sugar cubes.");

	}

	public static void main(String[] args) {
  
Coffee myOrder = new Coffee(); 
    myOrder.addSugar(2);
    myOrder.isFull();
	}
}
```
