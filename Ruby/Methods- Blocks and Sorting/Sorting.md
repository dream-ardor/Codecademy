METHODS, BLOCKS, & SORTING

Sorting

Finally, let's review what we learned about sorting.
```Ruby
books.sort! do |firstBook, secondBook|
  firstBook <=> secondBook
end
```
Remember that the above example was how we sorted in alphabetical order.

**Instructions:**
Use .sort! to sort the fruits array in descending (that is, reverse) alphabetical order. You can use the combined comparison operator (like the example above) or an if/elsif/else statement.

**My Code:**
```Ruby
fruits = ["orange", "apple", "banana", "pear", "grapes"]

fruits.sort! do |fruits1, fruits2|
  fruits2 <=> fruits1
end
```
