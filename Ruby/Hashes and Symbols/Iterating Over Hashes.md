HASHES AND SYMBOLS

Iterating Over Hashes

We can also iterate over hashes using the .each method. For example, we could do
```Ruby
my_hash.each do |key, value|
  puts my_hash[]
end
```
This will print out a list of keys and values from my_hash, each on its own line.

**Instructions:**
Iterate over the matz hash and print each value to the console using puts.

**My Code:**
```Ruby
matz = { "First name" => "Yukihiro",
  "Last name" => "Matsumoto",
  "Age" => 47,
  "Nationality" => "Japanese",
  "Nickname" => "Matz"
}

matz.each do |key, value|
  puts matz[key]
end
```
