A NIGHT AT THE MOVIES

Update

Perfect! Let's move on to the next branch of our case statement, which handles updating an existing movie in the hash. (This should be very similar to the work we did in the "add" branch!) We'll do this in three steps:

**Instructions:**
Inside your when "update" block, remove the puts "Updated!" statement.

Prompt the user for a movie title. Store it in title.

if the movies[title] is nil, then the movie is not in the hash. Please puts a string telling the user of their error.

Otherwise (else), we need to update the movies hash. Prompt the user for a new rating. Set the movie's rating to that new value.

Make sure to test it out!

**Solution:**
```ruby
movies = {
  StarWars: 4.8, 
  Divergent: 4.7
  }

puts "What would you like to do? "

choice = gets.chomp

case choice
when "add"
  puts "What movie would you like to add? "
  title = gets.chomp
  if movies[title.to_sym].nil? 
    puts "What rating does the movie have? "
    rating = gets.chomp
    movies[title.to_sym] = rating.to_i
  else
    puts "That movie already exists! Its rating is #{movies[title.to_sym]}."
  end
when "update"
  puts "What movie would you like to update? "
  title = gets.chomp
  if movies[title.to_sym].nil? 
    puts "That movie does not exist."
  else
    puts "What is the new rating? "
    rating = gets.chomp
    movies[title.to_sym] = rating.to_i
  end
when "display"
  puts "Movies!"
when "delete"
  puts "Deleted!"
else
  puts "Error!"
end
```
