## If-Then-Else
We’ve seen how to conditionally execute one block of code, but what if there are two possible blocks of code we’d like to execute?

Let’s say if a student has the required prerequisite, then they enroll in the selected course, else they’re enrolled in the prerequisite course instead.

We create an alternate conditional branch with the else keyword:
```java
if (hasPrerequisite) {

  // Enroll in course

} else {

  // Enroll in prerequisite

}
```
This conditional statement ensures that exactly one code block will be run. If the condition, hasPrerequisite, is false, the block after else runs.

There are now two separate code blocks in our conditional statement. The first block runs if the condition evaluates to true, the second block runs if the condition evaluates to false.

This code is also called an if-then-else statement:

If condition is true, then do something.

Else, do a different thing.
### Instructions

In the code editor, there is an isFilled value, that represents whether the order is ready to ship.

Write an if-then-else statement that:

- When isFilled is true, print Shipping.
- When isFilled is false, print Order not ready.

### :coffee:My Code
```java
public class Order {
  
  public static void main(String[] args) {
    
    boolean isFilled = true;
    
    // Write an if-then-else statement:
    if (isFilled) {
      System.out.println("Shipping");
    }
    else {
      System.out.println("Order not ready");
      
        
    }
  }
  
}
```
