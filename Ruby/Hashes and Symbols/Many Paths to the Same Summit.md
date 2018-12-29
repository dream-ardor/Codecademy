HASHES AND SYMBOLS

Many Paths to the Same Summit

Remember, there are always many ways of accomplishing something in Ruby. Converting strings to symbols is no different!

Besides using .to_sym, you can also use .intern. This will internalize the string into a symbol and works just like .to_sym:
```Ruby
"hello".intern
# ==> :hello
```
When you're looking at someone else's code, you might see .to_sym or .intern (or both!) when converting strings to symbols.

**Instructions:**
Update your code from the last exercise to use .intern instead of .to_sym.

**My Code:**
```Ruby
strings = ["HTML", "CSS", "JavaScript", "Python", "Ruby"]

# Add your code below!


symbols = []
strings.each do |s|
s1 = s.intern
symbols.push(s1)
end

print symbols
```
