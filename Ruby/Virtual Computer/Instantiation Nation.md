VIRTUAL COMPUTER

Instantiation Nation

Excellent! Last step: let's create an instance of our Computer class.

You've done this before, but here's a refresher.
```ruby
class Person
  def initialize(name)
    @name = name
  end
end

emma = Person.new("emma")
```

In the example above, we first define a Person class with an initialize method.
Then, we create a new instance of Person and store it in a new variable called emma.
**Instructions:**
After your class, create a new instance of Computer and store it in a new variable called my_computer. Feel free to use whatever username and password you like for your arguments!

**My Code:**
```ruby
class Computer
  @@users = {}
  def Computer.get_users
    return @@users
  end
  def initialize(username,password)
    @username = username
    @password = password
    @files = {}
    @@users[username] = password
    def create(filename)
      time = Time.now
      @files[filename] = time
      puts "A new file was created"
    end
  end
end

my_computer = Computer.new("Dan", "sexyman")
  
```
