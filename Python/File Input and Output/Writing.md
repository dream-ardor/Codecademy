Writing<br>
Good work! Now it's time to write some data to a new .txt file.

We added the list comprehension from the first exercise to the code in the editor. Our goal in this exercise will be to write each element of that list to a file called output.txt. The output.txt file that you write to will be created in your current folder - for simplicity, the folder has been hidden. output.txt will list each number on its own line.

We can write to a Python file like so:
```python
my_file.write("Data to be written")
```
The .write() method takes a string argument, so we'll need to do a few things here:

You must close the file. You do this simply by calling my_file.close() (we did this for you in the last exercise). If you don't close your file, Python won't write to it properly. From here on out, you gotta close your files!

**Instructions:**
Iterate over my_list to get each value.

Use my_file.write() to write each value to a text file called, output.txt.

Make sure to call str() on the iterating data so .write() will accept it.

Make sure to add a newline (+ "\n") after each element to ensure each will appear on its own line.

Use my_file.close() to close the file when you're done.

Passing the exercise means that you successfully wrote my_list to output.txt!

**Solution:**
```python
my_list = [i**2 for i in range(1,11)]

my_file = open("output.txt", "r+")

# Add your code below!

for i in my_list:
    my_file.write(str(i)+"\n")
    
my_file.close()
```
