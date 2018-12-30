A NIGHT AT THE MOVIES

The Case Statement

Good work! Now we'll want to create the main body of our program: the case statement, which will decide what actions to take based on what the user types in.

if and else are powerful, but we can get bogged down in ifs and elsifs if we have a lot of conditions to check. Thankfully, Ruby provides us with a concise alternative: the case statement. The syntax looks like this:
```ruby
case language
  when "JS"
    puts "Websites!"
  when "Python"
    puts "Science!"
  when "Ruby"
    puts "Web apps!"
  else
    puts "I don't know!"
end
```
The else is what the case statement will do if it doesn't match any of its when statements to the case (in this case, the value of language).

**Instructions:**
Below your existing code, create a case statement for the choice variable with the following when conditions:

when "add", please puts "Added!"
when "update", please puts "Updated!"
when "display", please puts "Movies!"
when "delete", please puts "Deleted!"
Otherwise (i.e. else), please puts "Error!"Don't forget the end statement after your case/when lines.

**My Code:**
```ruby
movies = {
  Deadpool: 4
  }

puts "Did you enjoy the movie?"
answer = choice.chomp

case choice
  when "add"
  puts "Added!"
  when "update"
  puts "Updated!"
  when "display"
  puts "Movies!"
  when "delete"
  puts "Deleted!"
else 
  puts "Error!"
end
```
