VIRTUAL COMPUTER

Who are the Users?

Perfect! Now that we think of it, though, we could have a whole bunch of users creating files every which where, and we don't have a way of getting to our @@users class variable! We'll need to create a method to reach it.

Because @@users is a class variable, we'll use a class method to grab it. Most of the methods you've seen so far are instance methods—they work on a particular instance/object, such as "matz" or "blixy". A class method belongs to the class itself, and for that reason, it's prefixed with the class name.
```ruby
class Machine
  def Machine.hello
    puts "Hello from the machine!"
  end
end
```
There's a shortcut for this, which we'll learn in a later lesson.

**Instructions:**
Add a new class method to your Computer class called Computer.get_users. It should have no parameters.

Your new Computer.get_users method should return the @@users class variable.

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
```
