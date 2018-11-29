A BIT of This AND That<br>
The bitwise AND (&) operator compares two numbers on a bit level and returns a number where the bits of that number are turned on if the corresponding bits of both numbers are 1. For example:
```python
     a:   00101010   42
     b:   00001111   15       
===================
 a & b:   00001010   10
 ```
As you can see, the 2's bit and the 8's bit are the only bits that are on in both a and b, so a & b only contains those bits. Note that using the & operator can only result in a number that is less than or equal to the smaller of the two values.

So remember, for every given bit in a and b:
```python
0 & 0 = 0
0 & 1 = 0
1 & 0 = 0
1 & 1 = 1
```
Therefore,
```python
0b111 (7) & 0b1010 (10) = 0b10
```
which equals two.

**Instructions:**
print out the result of calling bin() on 0b1110 & 0b101.

See if you can guess what the output will be!

**My Code:**
```python
print bin(0b1110 & 0b101)
```
