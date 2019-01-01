THE ZEN OF RUBY

In Case of Many Options

Excellent. Regular if/else statements aren't the only ones we can refactor, though—a chain of if/elsif/else statements can clean up really nicely, too!

**Instructions:**
Refactor the if/elsif/else statement in the editor into a tidy case statement.

**My Code:**
```ruby
puts "What's your favorite language?"
language = gets.chomp

case language
when "Ruby" then  "Ruby is great for web apps!"
when "Python" then "Python is great for science."
when "JavaScript" then  "JavaScript makes websites awesome."
when "HTML" then  "HTML is what websites are made of!"
when "CSS" then  "CSS makes websites pretty."
else 
puts "I don't know that language!"
end
```
