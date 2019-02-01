BUILD YOUR OWN MINI-BLOCKCHAIN!

Blockchain Summary

Congratulations! You have completed all the steps required to build a basic blockchain! In this exercise, we will bring the key parts together to review what we have built so far.

Note: The blockchain we have built only exists on a local machine. It is important to know that actual blockchain applications operate on multiple computers in a decentralized manner.

**Instructions:**
*Create a Blockchain object named local_blockchain. Verify that this automatically creates a Genesis Block by printing out the contents of local_blockchain.

*Individually add block_one_transactions, block_two_transactions, and block_three_transactions respectively into local_blockchain. Print out the contents of local_blockchain to see what the block holds.

*Modify the second block you added in local_blockchain by changing the block's transactions to fake_transactions. Check to see if the blockchain is still valid using the correct method.

**Solution:**
```js
from blockchain import Blockchain

block_one_transactions = {"sender":"Alice", "receiver": "Bob", "amount":"50"}
block_two_transactions = {"sender": "Bob", "receiver":"Cole", "amount":"25"}
block_three_transactions = {"sender":"Alice", "receiver":"Cole", "amount":"35"}
fake_transactions = {"sender": "Bob", "receiver":"Cole, Alice", "amount":"25"}

local_blockchain = Blockchain()
local_blockchain.print_blocks()

local_blockchain.add_block(block_one_transactions)
local_blockchain.add_block(fake_transactions)
local_blockchain.add_block(block_three_transactions)
local_blockchain.print_blocks()
local_blockchain.validate_chain()
```
