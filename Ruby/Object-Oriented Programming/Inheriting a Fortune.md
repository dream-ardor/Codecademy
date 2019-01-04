OBJECT-ORIENTED PROGRAMMING I

Inheriting a Fortune

Perfect! Now let's get in a little practice with inheritance.

**Instructions:**
Create a second class, Email, that inherits from Message. Give it its own initialize method that takes just one parameter, subject, and has one instance variable, @subject, set equal to subject.

```ruby
class Message 
  @@messages_sent = 0
  def initialize(from, to)
    @from = from 
    @to = to 
    @@messages_sent +=1 
  end
end

class Email < Message
  def initialize(subject)
    @subject = subject
  end
end

my_message = Message.new("Ian", "Alex")
```
