Using Methods: I

Great! Now the bark method is available to use on the spike object. We can do this by calling the method on spike.

Here is an example of calling a method on an object using the Car class:
```java
class Car {

    int modelYear;

    public Car(int year) {

        modelYear = year;

    }

    public void startEngine() {

        System.out.println("Vroom!");

    }
    
    public static void main(String[] args){

        Car myFastCar = new Car(2007);
        myFastCar.startEngine();
    }
```
In the example above, we call the startEngine method on the myFastCar object. Again, this occurs inside of the main method. Running the program results in printing Vroom! to the console.

**Instructions:**
Inside of the main method of the Dog class, call the bark method on the spike object.

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
    spike.bark();
	}
}
```
