OBJECT-ORIENTED JAVA

Inheritance

You've created a fully functional Dog class. Congratulations!

One of the object-oriented programming concepts that allows us to reuse and maintain code more efficiently is called inheritance. It is used to share or inherit behavior from another class. Let's look at an example:
```java
class Car extends Vehicle {

    int modelYear;

    public Car(int year) {

        modelYear = year;

    }

    //Other methods omitted for brevity...

    public static void main(String[] args){

        Car myFastCar = new Car(2007)
        myFastCar.checkBatteryStatus();

    }
}
class Vehicle {

    public void checkBatteryStatus() {

        System.out.println("The battery is fully charged and ready to go!");

    }
}
```
In the example above, the extends keyword is used to indicate that the Car class inherits the behavior defined in the Vehicle class. This makes sense, since a car is a type of vehicle.

Within the main method of Car, we call the checkBatteryStatus method on myFastCar. Since Car inherits from Vehicle, we can use methods defined in Vehicle on Car objects.

**Instructions:**
Note that there are now two files in the code editor. Within the Dog class, use the extends keyword to inherit from the Animal class.

Within the main method of the Dog class, call the checkStatus method on the spike object.

**My Code:**
```java
class Dog extends Animal {

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
  
  public int getAge() {
    
    return age;
  }

	public static void main(String[] args) {

    Dog spike = new Dog(10);
    spike.bark();
    spike.run(11);
    spike.checkStatus();
    int spikeAge = spike.getAge();
    System.out.println(spikeAge);
	}
}
```
