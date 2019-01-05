BANKING ON RUBY

Making a Withdrawal

Well done! Now let's add in our second public method, which will allow us to withdraw money from our account.

The trick to this one is to realize that since @balance can only be accessed from inside the class, we'll want to use @balance -= amount to decrease the balance by a certain amount.

**Instructions:**
Add a public withdraw method to your class that takes two parameters, pin_number and amount. If pin_number matches pin, your method should subtract the amount from the balance and puts "Withdrew #{amount}. New balance: $#{@balance}." Otherwise, it should puts pin_error.

**My Code:**
```ruby

class Account
  attr_reader :name, :balance
  def initialize(name, balance=100)
    @name = name
    @balance = balance
  end
  
  def display_balance(pin_number)
    puts pin_number == pin ? "Balance: $#{@balance}." : pin_error
  end
  
  def withdraw(pin_number, amount)
    if pin_number == pin
      @balance -= amount
      puts "Withdrew #{amount}. New balance: $#{@balance}."
    else
      puts pin_error
    end
  end
  
  private
  
  def pin
    @pin = 1234
  end
  
  def pin_error
    "Access denied: incorrect PIN."
  end
end
```
