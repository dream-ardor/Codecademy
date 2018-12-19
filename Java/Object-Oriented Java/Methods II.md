Methods: II

Fantastic! Similar to constructors, you can customize methods to accept parameters.
```java
class Car {

    int modelYear;

    public Car(int year) {

        modelYear = year;

    }

    public void startEngine() {
        System.out.println("Vroom!");
    }

    public void drive(int distanceInMiles) {

        System.out.println("Miles driven: " + distanceInMiles);

    }

    public static void main(String[] args){

        Car myFastCar = new Car(2007);
        myFastCar.startEngine();
        myFastCar.drive(1628);

    }
```
In the example above, we create a drive method that accepts an int parameter called distanceInMiles. In the main method, we call the drive method on the myFastCar object and provide an int parameter of 1628.

Calling the drive method on myFastCar will result in printing Miles driven: 1628 to the console.

**Instructions:**
In between the bark and main methods, add a method called run to the Dog class.

Modify the run method so that it accepts an int parameter called feet.

Inside of the run method, type:

System.out.println("Your dog ran " + feet + " feet!");

**My Code:**
```java
class Dog {

 int age;
 public Dog(int dogsAge) {
  age = dogsAge;

 }

 public void bark() {
  System.out.println("Woof!");
 }

 public void run(int feet) {
  System.out.println("Your dog ran " + feet + " feet!");

 }

 public static void main(String[] args) {

  Dog spike = new Dog(10);
  spike.bark();
  spike.run(11);
 }
}
```
