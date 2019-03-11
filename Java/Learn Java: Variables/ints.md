## LEARN JAVA: VARIABLES

### ints

The first type of data we will store is the whole number. Whole numbers are very common in programming. You often see them used to store ages, or maximum sizes, or the number of times some code has been run, among many other uses.

In Java, whole numbers are stored in the int primitive data type.

ints hold positive numbers, negative numbers, and zero. They do not store fractions or numbers with decimals in them.

The int data type allows values between -2,147,483,648 and 2,147,483,647, inclusive.

To declare a variable of type int, we use the int keyword before the variable name:
```java
// int variable declaration
int yearJavaWasCreated;
// assignment
yearJavaWasCreated = 1996;
// declaration and assignment
int numberOfPrimitiveTypes = 8;
```
### Instructions

The file CountComment.java has a number of comments in it.

In your head, count the number of comments. Then, inside the main() method, declare a variable called numComments that holds how many comments you counted.

Print out numComments.

## My Code
```java
//This is the class declaration
public class CountComment {
  //This is the main method that runs when you compile
	public static void main(String[] args) {
    //This is where you will define your variable
    int numComments = 6;
    //This is where you will print your variable
    System.out.println(numComments);
    
	}
  
  //This is the end of the class
}

//This is outside the class
```
