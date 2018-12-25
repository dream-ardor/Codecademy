DATA STRUCTURES

ArrayList: Insertion

We can also insert new elements into an ArrayList.

To insert new elements into an ArrayList, we can use a slightly different version of the add method that you previously used:
```java
ArrayList<Integer> quizGrades = new ArrayList<Integer>();
quizGrades.add(95);
quizGrades.add(87);
quizGrades.add(73);

quizGrades.add(0, 100);
System.out.println( quizGrades.get(0) );
```
The example above will print out the grade 100.

The add method will insert the grade 100 at the first position (0) into the list. Since it inserts a new element into the beginning of the ArrayList, all other element indices will be shifted one position higher. The grade 95 is now at index 1.

**Instructions:**
Insert a new temperature of 111 at index 2.

On the next line, use the get method to print out the temperature 89.

**My Code:**
```java
import java.util.ArrayList;

public class TemperaturesB {
	
	public static void main(String[] args) {

		ArrayList<Integer> weeklyTemperatures = new ArrayList<Integer>();
		weeklyTemperatures.add(78);
		weeklyTemperatures.add(67);
		weeklyTemperatures.add(89);
		weeklyTemperatures.add(94);

 weeklyTemperatures.add(2, 111);
 System.out.println( weeklyTemperatures.get(3) );
	}
}
```
