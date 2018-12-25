DATA STRUCTURES

HashMap: Manipulation

Perfect! Now let's fill the HashMap with useful data.

Add keys and values to a HashMap:
```java
HashMap<String, Integer> myFriends = new HashMap<String, Integer>();

myFriends.put("Mark", 24);
myFriends.put("Cassandra", 25);
myFriends.put("Zenas", 21);
```
In the example above, we used the put method to add a String key and an associated Integer value. The String key is the text inside double quotes " ". The Integer value is represented by the number.

**Instructions:**
Let's add some food items and prices to the our menu. Use the put method to add a key "Turkey Burger" with the value 13.

Add a key "Naan Pizza" with the value 11.

Finally, add a key "Cranberry Kale Salad" with the value 10.

**My Code:**
```java
import java.util.HashMap;

public class Restaurant {
	public static void main(String[] args) {

HashMap<String, Integer> restaurantMenu = new
HashMap<String, Integer>();
    
    
 restaurantMenu.put("Turkey Burger", 13);
 restaurantMenu.put("Naan Pizza", 11);
 restaurantMenu.put("Cranberry Kale Salad", 10);
   
	}
}
```
