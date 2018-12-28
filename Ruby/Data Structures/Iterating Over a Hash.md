DATA STRUCTURES

Iterating Over a Hash

We've done a fair amount of iteration over arrays, so to finish up, let's review how to iterate over a hash.
```Ruby
numbers = [1, 2, 3, 4, 5]
numbers.each { |element| puts element }
```
**Instructions:**
Iterate through .each key/value pair in lunch_order.

Please puts out the value of each pair (just the value, not the key).

**My Code:**
```Ruby
lunch_order = {
  "Ryan" => "wonton soup",
  "Eric" => "hamburger",
  "Jimmy" => "sandwich",
  "Sasha" => "salad",
  "Cole" => "taco"
}

lunch_order.each { |name, order| puts order}
```
