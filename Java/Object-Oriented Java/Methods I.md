Methods: I

Great work! We created a Dog object inside of the main method, but...nothing happened.

Although we created an object inside of main method, we did not print out anything about the spike object itself, nor did we instruct the class to perform any actions. Let's learn about how methods in Java are used to define actions.

A method is a pre-defined set of instructions. Methods are declared within a class. Java provides some pre-defined methods available to all classes, but we can create our own as well.

Let's create a new method:
```java
class Car {

    int modelYear;

    public Car(int year) {

        modelYear = year;

    }

    //Our new method to help us get "started"
    public void startEngine() {

        System.out.println("Vroom!");

    }

    public static void main(String[] args){

        Car myFastCar = new Car(2007);

    }
}
```
In the example above, we added a method called startEngine. When the method is used, it will print out Vroom!. The void keyword will be explained later in this course.

Note that the startEngine method is created outside of the main method, like the constructor was.

**Instructions:**
In between the constructor and the main method, add a method called bark to the Dog class.

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

 public static void main(String[] args) {

  Dog spike = new Dog(10);
 }
}
```

