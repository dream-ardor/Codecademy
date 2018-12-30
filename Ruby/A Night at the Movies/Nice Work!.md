A NIGHT AT THE MOVIES

Nice Work!

Fantastic! You built a little app with only a few dozen lines of code. Impressive, isn't it?

The four verbs your program knows—add, display, update, and delete—are universal. This acronym is better known as CRUD for create, read, update, and delete (respectively). These are the actions you take when you update an entry in a database, ask a website for information, or write a blog post. Being familiar with this setup is good, because you'll see it in everything from API calls to web frameworks like Ruby on Rails.

**Instructions:**
Feel free to play around with your program until you've got it running just the way you like it. (Maybe add a more specific else message than "Error!"?)

When you're ready, click Run to complete this project!

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
