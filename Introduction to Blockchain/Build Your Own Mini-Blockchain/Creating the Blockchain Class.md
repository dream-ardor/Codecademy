BUILD YOUR OWN MINI-BLOCKCHAIN!

Creating the Blockchain Class

Each computer participant has their own copy of the blockchain. Ideally, each copy of the blockchain should have the same properties and functionality to add and validate blocks.

We can represent the blockchain as an object. We are using objects for our implementation, because they offer the flexibility to create specific attributes and methods. Representing it as an object also allows us to create blockchain instances for each computer participant.

To review, our blockchain contains the following:

Chain: A list that that holds all the blocks inside the blockchain.
Unverified Transactions: A list that represents all the unverified transactions before being passed into a block.
Genesis Block: A block automatically generated when the blockchain is initialized.

**Instructions:**
Fill in the __init__() method inside the Blockchain class by initializing instance variables chain and all_transactions as empty Python lists.

Complete the method genesis_block by instantiating a new Block object with an empty transactions list and a previous hash of 0.

Append the resulting block to the chain.

Since we want to automatically create a Genesis Block when a new blockchain object is created, call the method .genesis_block() inside the __init__() method.

**Solution:**
```python
#imports the Block class from block.py
from block import Block

class Blockchain:
    def __init__(self):
      self.chain = []
      self.all_transactions = []
      self.genesis_block()
    
    def genesis_block(self):
      transactions = []
      previous_hash = "0"
      self.chain.append(Block(transactions, previous_hash))
    
```
