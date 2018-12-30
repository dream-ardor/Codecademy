A NIGHT AT THE MOVIES

Delete

Almost there! Let's handle the "delete" part of our case statement, which will remove whatever key the user specifies from the hash. (This will be very similar to what we did for "add" and "update.")

Ruby makes it easy to remove a movie/rating pair from our hash: we just write movies.delete(title)!

**Instructions:**
Go ahead and remove the puts "Deleted!" when the user types "delete".

Get the title from the user.

Include an if/else statement that puts an error if the movie's not in the hash; if it's there, use .delete to remove it as shown above.Make sure to test it out!

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
  movies.each do |title, rating| 
    puts "#{title}: #{rating}"
  end
when "delete"
  puts "What movie would you like to delete? "
  title = gets.chomp
 if movies[title.to_sym].nil? 
   puts "That movie does not exist."
 else
   puts movies.delete(title)
 end
else
  puts "Error!"
end
```
