DATA STRUCTURES

ArrayList: Manipulation

You created an ArrayList in the last exercise to store temperature data, but it does not contain any values yet.

Let's add some values of type Integer to the ArrayList, one by one, like this:
```java
ArrayList<Integer> quizGrades = new ArrayList<Integer>();
quizGrades.add(95);
quizGrades.add(87);
quizGrades.add(83);
```
In the example above, we call the add method on quizGrades. The add method adds integers to the ArrayList. The values 95, 87, and 83 are added to the list.

**Instructions:**
Add some temperatures to weeklyTemperatures. First, add a temperature value of 78.
Next, add a temperature of 67.
Add another temperature of 89.
Finally, add a temperature of 94.

**My Code:**
```java
import java.util.ArrayList;

public class Temperatures {
	
	public static void main(String[] args) {

    ArrayList<Integer> weeklyTemperatures = new
      ArrayList<Integer>();
    weeklyTemperatures.add(78);
    weeklyTemperatures.add(67);
    weeklyTemperatures.add(89);
    weeklyTemperatures.add(94);

	}
}
```
