BUILD YOUR OWN MINI-BLOCKCHAIN!

Creating Blocks

Now let's think of a way to represent a block in Python. We could create a bigger dictionary and store our data inside this dictionary. But since blocks can be represented as objects, let's create a Block Class which we can easily use to create new blocks.

Recall that a Block contains the following properties:
```python
Timestamp
Transaction
Hash
Previous Hash
Nonce
```
In this exercise, we will be creating the default constructor for the Block class in our Mini-Blockchain.

**Instructions:**

Every Block in the blockchain has a timestamp associated with it. In order to dynamically generate a timestamp, we must import a Python module that returns the current date and time.

Import the datetime module from the datetime library.

Inside the datetime module there is a .now() method that returns the current date and time.

Call the datetime module's .now() method to print out the current date and time.

Now let's work on creating our Block. We will be passing transactions and previous_hash to the default constructor each time a Block is created.

Complete the __init__() method inside the Block class by initializing the following instance variables:
```python
transactions
previous_hash
nonce (with a default value of 0).
```
Inside the __init__() method, create a timestamp instance variable that stores the current date and time.

**Solution:**
```python
# import datetime library
from datetime import datetime
# print current date and time
print(datetime.now())

class Block:
# default constructor for block class
  def __init__(self, transactions, previous_hash, nonce = 0):
    self.transactions = transactions
    self.previous_hash = previous_hash
    self.nonce = nonce
    self.timestamp = datetime.now()
```
