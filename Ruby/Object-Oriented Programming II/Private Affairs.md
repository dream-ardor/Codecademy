OBJECT-ORIENTED PROGRAMMING II

Private Affairs

Good! Now let's try a private method.

**Instructions:**
Below your public method, add a private method called password that returns the super secret password 12345.

**My Code:**
```ruby
class Application
  attr_accessor :status
  def initialize; end
  public
  def print_status
    puts "All systems go!"
  end
  # Add your method here!
  private
  def password
    return 12345
  end
end
```
