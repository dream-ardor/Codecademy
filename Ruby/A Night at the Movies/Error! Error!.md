A NIGHT AT THE MOVIES

Error! Error!

All right! We're nearly done with the "add" part of our case. The final thing we'll want to do is perform a check to see whether the movie to be added is already in the hash.

To do this, we'll add an if/else statement.

**Instructions:**
Add an if/else statement to the add branch of your case. If the movie isn't already in the hash (that is, if movies[title.to_sym] is nil), it should add the movie/rating pair; otherwise, it should puts that the movie already exists and not add anything to the hash. Make sure to test it!

**Solution:**
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
    if movies[title.to_sym].nil?
    puts "What's the rating? (Type a number 0 to 4.)"
  puts "Please enter a rating"
  rating = choice.chomp
  movies[title.intern] = rating.to_i
  puts "#{title} has been added with a rating of #{rating}"
       else
    puts "That movie already exists! Its rating is #{movies[title.to_sym]}."
  end
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
