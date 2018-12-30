A NIGHT AT THE MOVIES

Not My Type

Perfect! Our program is really coming along.

You might have wondered how we're going to get our movies and ratings from the user—which come in as strings—into the hash where we want our movies to be symbols and our ratings to be integers. Built-in Ruby magic to the rescue!

Ruby's .to_sym method can convert a string to a symbol, and .to_i will convert a string to an integer.

**Instructions:**
Call .to_sym on your title and .to_i on your rating so that your movie titles are stored as symbols in the hash and the associated ratings are stored as integers.

**My Code:**
```ruby
movies = {
  Deadpool: 4,
  }


puts "Did you enjoy the movie?"
answer = choice.chomp

case choice
  when "add"
  puts "Please enter a movie title"
  title = choice.chomp
  puts "Please enter a rating"
  rating = choice.chomp
  movies[title.intern] = rating.to_i
  puts "#{title} has been added with a rating of #{rating}"
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
