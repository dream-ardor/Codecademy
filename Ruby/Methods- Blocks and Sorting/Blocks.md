METHODS, BLOCKS, & SORTING

Blocks

Let's go over what we learned about blocks.
```Ruby
numbers = [5, 2, 8]
sum = 0
numbers.each do |n|
  sum += n
end
puts sum
```
The example above is just a reminder about syntax. We calculate the sum of a list of numbers.

**Instructions:**
Add a block after .each that multiplies each item by itself and puts the result to the console.

**My Code:**
```Ruby
my_array = [1, 2, 3, 4, 5]

my_array.each do |n|
  sum = n*n
  puts sum
end
```
