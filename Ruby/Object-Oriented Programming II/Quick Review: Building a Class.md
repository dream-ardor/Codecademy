OBJECT-ORIENTED PROGRAMMING II

Quick Review: Building a Class

Let's build a class!
```ruby
class ClassName
  def method_name(parameter)
    @class_Variable = parameter
  end
end
```
First we tell Ruby that we want to construct our class ClassName. Don't forget the end to end your class!
Inside our ClassName is where we define our methods. Here we have MethodName followed by (parameter), When we use this method it will look like this MethodName("hello!")
If our parameter above were "Hello!" it would be assigned to our variable @classVariable on the following line.
Again, don't forget to end your MethodName!

**Instructions:**
First, create a class named Dog

Create a method initialize within your class Dog.

Allow your initialize method to accept two parameters, name and breed.

Inside your initialize method assign those two parameters to the variables @name and @breed respectively

**My Code:**
```ruby
class Dog
  def initialize(name,breed)
    @name = name
    @breed = breed
  end
end
```
