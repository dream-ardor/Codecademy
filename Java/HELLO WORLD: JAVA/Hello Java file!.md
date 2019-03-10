## HELLO WORLD: JAVA

### Hello Java File!

Java runs on different platforms, but programmers write it the same way. Let's explore some rules for writing Java using the previous exercise as an example.

We started in the file HelloWorld.java. Java files have a .java extension. Some programs are one file, others are dozens or hundreds of files!

Inside HelloWorld.java, we had a class:
```java
public class HelloWorld {

}
```
We'll talk about classes in detail in the future, but for now think of them as a single concept.

The HelloWorld concept is: A Hello World Printer. Other examples of class concepts could be: A Bicycle, or: A Savings Account.

We marked the domain of this concept using curly braces: {}. All syntax inside the curly braces is part of the class.

Each file has one primary class with the same name as the file. Our class is named HelloWorld and our file is named HelloWorld. Every word is capitalized.

Inside the class we had a main() method which contained the tasks our class performed:
```java
public static void main(String[] args) {

}
```
Like classes, we used curly braces to mark the beginning and end of a method.

Our program printed "Hello World" with the line:
```java
System.out.println("Hello World");
```
### Instructions

The text editor has a file, HelloYou.java, that contains a HelloYou class with a main() method.

Inside main(), add a statement which prints Hello someName!, with your name replacing someName.

For example, my program would print Hello Patrick!.

## My Code
```java
public class HelloYou {
  public static void main(String[] args) {
    System.out.println("Hello Dan!");
    
  }
}
```
