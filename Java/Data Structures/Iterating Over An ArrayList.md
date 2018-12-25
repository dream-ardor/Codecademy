DATA STRUCTURES

Iterating over an ArrayList

Earlier in this lesson, we learned about the for loop. Since we've also learned how to retrieve the value at a specific index of an ArrayList, we can now access each of the elements.
```java
for (int i = 0; i < quizGrades.size(); i++) {

    System.out.println( quizGrades.get(i) );

}
```
In the example above, the for loop above includes the following statements:

Initialization: int variable i is set to 0 which is the first index of an ArrayList.
Test condition: the code in the block will run as long as i is less than the size of quizGrades.
Increment: The code in this block will execute after each loop. In this case,i will increment by 1 with i++ after each loop.
The size method returns an int that represents how many total elements are stored within quizGrades. The example will print out each element within quizGrades in order. The process of going through each element in the ArrayList is called iteration.

**Instructions:**
Inside of a for loop, print out the elements of the weeklyTemperatures ArrayList. Use the get method and the int variable j. You can use the example above as reference.

**My Code:**
```java
import java.util.ArrayList;

public class TemperaturesC {
	
	public static void main(String[] args) {

		ArrayList<Integer> weeklyTemperatures = new ArrayList<Integer>();
		weeklyTemperatures.add(78);
		weeklyTemperatures.add(67);
		weeklyTemperatures.add(89);
		weeklyTemperatures.add(94);
		weeklyTemperatures.add(2, 111);

		for (int j = 0; j < weeklyTemperatures.size(); j++) {
      System.out.println( weeklyTemperatures.get(j) );
    }

	}
}
```
