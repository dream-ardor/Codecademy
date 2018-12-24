DATA STRUCTURES

For Loop

When you provide a set of instructions in a method, you might find that a common task is to manipulate an entire set of data. Java conveniently provides control statements to run a task repeatedly. The control statement we will explore is called the for loop.

The for loop repeatedly runs a block of code until a specified condition is met.

The example below shows how a for loop is used:
```java
for (int counter = 0; counter < 5; counter++) {

    System.out.println("The counter value is: " + counter);

}
```
The statements within the parentheses of for loop compose the following parts:

1. Initialization: the int variable named counter is initialized to the value of 0 before the loop is run.

2. Test condition: the Boolean expression counter < 5 is a conditional statement that is evaluated before the code inside the control statement is run every loop. If the expression evaluates to true, the code in the block will run. Otherwise, if the expression evalutes to false, the for loop will stop running.

3. Increment: Each time the loop completes, the increment statement is run. The statement counter++ increases the value of counter by 1 after each loop.

In the example above, the for loop initially executes the code block in the sample code above because the initial value of counter is less than 5, which passes the test condition.

The value of counter is then incremented by 1 in the increment.
The code block will execute again because counter is still less than 5. This cycle will continue until counter is no longer less than 5.

Please note that similar to the if-then statement, no semicolon is necessary.

**Instructions:**
The for loop in the code editor is currently missing the three statements required to execute the code in the block. Finish the for loop by typing:
```java
for (int waterLevel = 0; waterLevel < 7; waterLevel++) {

}
```
Leave the rest of the code inside the for loop as is.

**My Code:**
```java
public class For {
	public static void main(String[] args) {

		for (int waterLevel = 0; waterLevel < 7; waterLevel++) {

			System.out.println("The pool's water level is at " + waterLevel + " feet.");

		}
		
	}

}
```
