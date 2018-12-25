DATA STRUCTURES

For Each Loop

Since most for loops are very similar, Java provides a shortcut to reduce the amount of code required to write the loop called the for each loop.

Here is an example of the concise for each loop:
```java
for (Integer grade : quizGrades){
    System.out.println(grade);
}
```
In the example above, the colon (:) can be read as "in". The for each loop altogether can be read as "for each Integer element (called grade) in quizGrades, print out the value of grade."

The loop will print out the value of each Integer element in quizGrades.

Note: the for each loop does not require a counter.

**Instructions:**
The current block of code in the code editor is incomplete. Finish the for each loop by typing:
```java
for (Integer temperature : weeklyTemperatures) {
    System.out.println(temperature);
}
```
