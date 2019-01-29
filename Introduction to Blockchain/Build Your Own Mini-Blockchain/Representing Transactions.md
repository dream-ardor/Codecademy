BUILD YOUR OWN MINI-BLOCKCHAIN!

Representing Transactions

In this lesson, you'll build a small blockchain of your own in Python! This lesson assumes a familiarity with Python syntax, functions, loops, importing libraries, and constructing classes, but there are some hints along the way to help out. If you've never used Python before, you might want to learn some with Codecademy.

The blockchain is a new way of storing and moving data securely. The data mostly consists of transactions which include messages exchanged between two parties. Before we start creating our blockchain, let's think of a way to store a transaction like the one shown below:
```python
amount: 30
sender: Alice
receiver: Bob
```
In this example, Alice is trying to transfer 30 units of some currency to Bob. Can you think of a Python data type to best represent the above transaction?

This transaction is best represented in the form of a Python dictionary, with keys for the required fields and values specific to the transaction.

These transactions are all stored inside the mempool, a pool of transactions that miners reference when selecting the set of transactions they want to verify.

**Instructions:**

*Let's create a transaction and add it to the mempool. Name the new transaction my_transaction and add amount, sender, and receiver as key-values.

*Add my_transaction to the mempool list.

*Create a new list called block_transactions and add three transactions from the mempool list. This will allow us to prepare the transactions to be added to our future Block structure.

**My Code:**
```python
transaction1 = {
  'amount': '30',
  'sender': 'Alice',
  'receiver': 'Bob'}
transaction2 = { 
  'amount': '200',
  'sender': 'Bob',
  'receiver': 'Alice'}
transaction3 = { 
  'amount': '300',
  'sender': 'Alice',
  'receiver': 'Timothy' }
transaction4 = { 
  'amount': '300',
  'sender': 'Rodrigo',
  'receiver': 'Thomas' }
transaction5 = { 
  'amount': '200',
  'sender': 'Timothy',
  'receiver': 'Thomas' }
transaction6 = { 
  'amount': '400',
  'sender': 'Tiffany',
  'receiver': 'Xavier' }

mempool = [transaction1, transaction2, transaction3, transaction4, transaction5, transaction6]

# add your code below

my_transaction = {
  'amount': '69',
  'sender': 'Kim',
  'receiver': 'Dan'
}

mempool.append(my_transaction)

block_transactions = [transaction1, transaction6,my_transaction]
```
