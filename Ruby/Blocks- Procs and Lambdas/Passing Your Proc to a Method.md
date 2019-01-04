BLOCKS, PROCS, AND LAMBDAS

Passing Your Proc to a Method

Perfect! Now let's pass our proc to a method.

**Instructions:**
Now we'll be using the ages array. Create a variable called youngsters and set it equal to calling .select on ages, and pass in your under_100 proc to filter for the ages that are less than one hundred. Remember to pass &under_100 to convert your proc to a block!

puts youngsters at the end of the file in order to see the final contents of the array.

**My Code:**
```ruby
ages = [23, 101, 7, 104, 11, 94, 100, 121, 101, 70, 44]

# Add your code below!

under_100 = Proc.new { |x| x < 100}

youngsters = ages.select(&under_100)

puts youngsters
```
