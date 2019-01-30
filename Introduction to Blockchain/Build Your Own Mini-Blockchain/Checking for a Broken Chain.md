BUILD YOUR OWN MINI-BLOCKCHAIN!

Checking for a Broken Chain

Hashing helps to maintain the integrity of the blockchain. In this exercise, we will see this in action. Let’s write a .validate_chain() method that checks to see if blocks are linked to each other properly.

In order to validate the entire blockchain, we must loop through each of the blocks stored inside the blockchain itself. Then, we will check through each of the blocks to ensure that the previous hash value matches with the hash value inside our previous block.

**Instructions:**
In the .validate_chain() method, create a for loop with the loop variable i and traverse through the entire length of self.chain. Be sure to start at index 1 instead of index 0.

Inside the for loop, create a variable current and assign it to the current block being indexed with i. Create another variable previous and assign it to the previous block using index i-1.

Loop through the correct part of the chain with the following snippet:

for i in range(1, len(self.chain)):

Verify that the hash of the current block is NOT equal to the value the current block generates via the generate_hash() method. If this condition is true, then the blockchain is not valid, therefore we should return False.

Verify that the hash of the previous hash of the current block is NOT equal to the value generated over the previous block using the generate_hash() method. If this condition is true, then the blockchain is not valid, therefore we should return False.

If the above conditions are not satisfied, then the blockchain is valid! Return True outside the for loop.

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
    transactions = {}
    genesis_block = Block(transactions, "0")
    self.chain.append(genesis_block)
    return self.chain

  # prints contents of blockchain
  def print_blocks(self):
    for i in range(len(self.chain)):
      current_block = self.chain[i]
      print("Block {} {}".format(i, current_block))
      current_block.print_contents()    
  
  # add block to blockchain `chain`
  def add_block(self, transactions):
    previous_block_hash = self.chain[len(self.chain)-1].hash
    new_block = Block(transactions, previous_block_hash)
    self.chain.append(new_block)

  def validate_chain(self):
    for i in range(1, len(self.chain)):
      current = self.chain[i]
      previous = self.chain[i-1]
      if(current.hash != current.generate_hash()):
        print("The current hash of the block does not equal the generated hash of the block.")
        return False
      if(current.previous_hash != previous.generate_hash()):
        print("The previous block's hash does not equal the previous hash value stored in the current block.")
        return False
    return True
```
