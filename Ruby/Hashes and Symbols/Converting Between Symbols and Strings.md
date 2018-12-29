HASHES AND SYMBOLS

Converting Between Symbols and Strings

Converting between strings and symbols is a snap.
```Ruby
:sasquatch.to_s
# ==> "sasquatch"

"sasquatch".to_sym
# ==> :sasquatch
```
The .to_s and .to_sym methods are what you're looking for!

**Instructions:**
We have an array of strings we'd like to later use as hash keys, but we'd rather they be symbols.

Create a new variable, symbols, and store an empty array in it.
Use .each to iterate over the strings array.
For each s in strings, use .to_sym to convert s to a symbol and use .push to add that new symbol to symbols.
Print the symbols array.

**Solution:**
```Ruby
strings = ["HTML", "CSS", "JavaScript", "Python", "Ruby"]

# Add your code below!


symbols = []
strings.each do |s|
s1 = s.to_sym
symbols.push(s1)
end

print symbols
```
