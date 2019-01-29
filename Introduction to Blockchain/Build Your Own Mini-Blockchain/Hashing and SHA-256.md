BUILD YOUR OWN MINI-BLOCKCHAIN!

Hashing and SHA-256

Before we create a more dynamic blockchain, let’s learn how to use a hash function in Python. Specifically, we will be using the SHA-256 hash function which can be easily imported in Python.

We will use the SHA-256 as a regular function that takes in a random string as its argument. To properly use this function in Python 3, our string must be encoded before being passed as an argument. To encode the string, we use the .encode() method.

**Instructions:**
Import sha256 from the hashlib Python library.

Create a variable called text. Initialize the variable with this string I am excited to learn about blockchain.

Create a sha256 hash object, using the constructor sha256() and pass the text variable as its argument. Assign the value of this object to a variable called hash_result.

Be sure to use the .encode() method on the text variable.

Call the .hexdigest() method on hash_result and print the result.

Modify the text variable by adding an exclamation mark at the end and running your code.

Notice how this hash is completely different from the last one?

**My Code:**
```python
# import sha256
from hashlib import sha256
# text to hash
text = "I am excited to learn about blockchain!"
hash_result = sha256(text.encode())
# print result
print (hash_result.hexdigest())
```
