
OBJECT-ORIENTED PROGRAMMING I

Forge an Object in the Fires of Mount Ruby

Perfect! Let's go ahead and create an instance of our Message class.

**Instructions:**
After your class, create a variable called my_message.

Create an instance of your Message class using Message.new with whatever from and to arguments you want! Store the result in my_message.

**My Code:**
```ruby
class Message
  @@messages_sent = 0
  def initialize(from,to)
    @from = from
    @to = to
    @@messages_sent += 1
  end
end

my_message = Message.new("Dan","Is Awesome")
```
