## LEARN JAVA: MANIPULATING VARIABLES

### Introduction

Let’s say we are writing a program that represents a user’s bank account.

With variables, we know how to store a balance! We’d use a double, the primitive type that can hold big decimal numbers.

But how would we deposit and withdraw from the account?

Java has built-in math operations that perform calculations on numeric values!

To deposit:
```java
// declare initial balance
double balance = 20000.99;
// declare deposit amount
double depositAmount = 1000.00;
// store result of calculation in new variable
double updatedBalance = balance + depositAmount;
```
Throughout this lesson, we will learn how to perform math on different datatypes and compare values.

### Instructions

In the file GuessingGame.java, we have defined two integers mystery1 and mystery2.

We will talk about these operators, among others, in the rest of the lesson.

Use System.out.println() to print the variable that holds a value of 2.

## My Code
```java
public class GuessingGame {
	public static void main(String[] args) {   
		int mystery1 = 8 + 6;
    int mystery2 = 8 - 6;
    System.out.println(mystery2);
	}
}
```
