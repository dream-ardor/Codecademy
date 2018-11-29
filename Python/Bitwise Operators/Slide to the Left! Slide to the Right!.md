Slide to the Left! Slide to the Right!<br>
The next two operations we are going to talk about are the left and right shift bitwise operators. These operators work by shifting the bits of a number over by a designated number of slots.

The block below shows how these operators work on the bit level. Note that in the diagram, the shift is always a positive integer:
```python
# Left Bit Shift (<<)  
0b000001 << 2 == 0b000100 (1 << 2 = 4)
0b000101 << 3 == 0b101000 (5 << 3 = 40)       

# Right Bit Shift (>>)
0b0010100 >> 3 == 0b000010 (20 >> 3 = 2)
0b0000010 >> 2 == 0b000000 (2 >> 2 = 0)
```
Shift operations are similar to rounding down after dividing and multiplying by 2 (respectively) for every time you shift, but it's often easier just to think of it as shifting all the 1s and 0s left or right by the specified number of slots.

Note that you can only do bitwise operations on an integer. Trying to do them on strings or floats will result in nonsensical output!

**Instructions:**
Shift the variable shift_right to the right twice (>> 2) and shift the variable shift_left to the left twice (<< 2). Try to guess what the printed output will be!

**My Code:**
```python
shift_right = 0b1100 >> 2
shift_left = 0b1 << 2

# Your code here!


print bin(shift_right)
print bin(shift_left)
```
