DATA STRUCTURES

HashMap

Great! Another useful built-in data structure in Java is the HashMap.

Although the name of the data structure might not make sense to you immediately, think of it as a real-life dictionary. A dictionary contains a set of words and a definition for each word. A HashMap contains a set of keys and a value for each key.

If we look up a word in a dictionary, we can get the definition. If you provide a HashMap with a key that exists, you can retrieve the value associated with the key.

Declaring a HashMap is shown in the following example:
```java
HashMap<String, Integer> myFriends = new HashMap<String, Integer>();
```
In the example above, we create a HashMap object called myFriends. The myFriends HashMap will store keys of String data types and values of type Integer.

Note: the String object allows you to store multiple characters, such as a word in quotations (e.g. "Rats!").

**Instructions:**
Create a HashMap object called restaurantMenu. The HashMap should store String keys and Integer values. Use the syntax in the example above if you need.

**My Code:**
```java
import java.util.HashMap;

public class Restaurant {
	public static void main(String[] args) {

HashMap<String, Integer> restaurantMenu = new
HashMap<String, Integer>();
    }
}
```
