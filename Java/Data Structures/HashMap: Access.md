DATA STRUCTURES

HashMap: Access

To access data in an ArrayList, we specified the index. In order to access a value in a HashMap, we specify the key:
```java
HashMap<String, Integer> myFriends = new HashMap<String, Integer>();

myFriends.put("Mark", 24);
myFriends.put("Cassandra", 25);
myFriends.put("Zenas", 21);

System.out.println( myFriends.get("Zenas") );
```
In the example above, we call the get method on the myFriends HashMap using the key "Zenas". The console will print the value associated with "Zenas" which is 21.

**Instructions:**
Use the get method to print out the price of the "Naan Pizza" item.

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
    
    System.out.println( restaurantMenu.get("Naan Pizza") );
   
	}
}
```
