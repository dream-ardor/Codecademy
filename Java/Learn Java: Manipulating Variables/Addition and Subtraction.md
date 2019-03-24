## LEARN JAVA: MANIPULATING VARIABLES

### Addition and Subtraction

In our bank account example from the last exercise, we used + to add!
```java
double balance = 20000.99;
double depositAmount = 1000.0;
double updatedBalance = balance + depositAmount;
//updatedBalance now holds 21000.99
```
If we wanted to withdraw from the balance, we would use -:
```java
double withdrawAmount = 500;
double updatedBalance = balance - withdrawAmount;
//updatedBalance now holds 19500.99
```
Addition and subtraction work with ints as well!
```java
int numPicturesOfCats = 60 + 24;
```
If you had 60 pictures of cats on your phone, and you took 24 more, you could use the above line of code to store 84 in numPicturesOfCats.

### Instructions

Create an int variable called animalsInZoo that holds the amount of zebras plus the amount of giraffes at the zoo.

Then, print your animalsInZoo variable.

Two of the zebras have been traded to a neighboring rival zoo. Subtract 2 from the number of zebras and store the result in a variable called numZebrasAfterTrade.

Then, print the numZebrasAfterTrade variable!

## My Code
```java
public class PlusAndMinus {
	public static void main(String[] args) {   
		int zebrasInZoo = 8;
    int giraffesInZoo = 4;
    int animalsInZoo = zebrasInZoo + giraffesInZoo;
    System.out.println(animalsInZoo);
    
    int numZebrasAfterTrade = zebrasInZoo-2;
    System.out.println(numZebrasAfterTrade);
	}
}
```
