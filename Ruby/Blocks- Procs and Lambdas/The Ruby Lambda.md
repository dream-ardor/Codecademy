BLOCKS, PROCS, AND LAMBDAS

The Ruby Lambda

Like procs, lambdas are objects. The similarities don't stop there: with the exception of a bit of syntax and a few behavioral quirks, lambdas are identical to procs.

Check out the code in the editor. See the lambda bit? Typing
```ruby
lambda { puts "Hello!" }
```
Is just about the same as
```ruby
Proc.new { puts "Hello!" }
```
In the example to the right, when we pass the lambda to lambda_demo, the method calls the lambda and executes its code.

**Instructions:**
Now that you know how blocks and procs work, you should be able to guess what this lambda will puts to the console. Click Run to confirm your suspicions!

```ruby
def lambda_demo(a_lambda)
  puts "I'm the method!"
  a_lambda.call
end

lambda_demo(lambda { puts "I'm the lambda!" })
```
