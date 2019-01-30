BUILD YOUR OWN MINI-BLOCKCHAIN!

Nonce and Proof-of-Work

Let's review the concepts of nonce and proof of work. In this exercise, we will implement an example that demonstrates the difficulty of the math problem that helps protect the blockchain from potential attackers.

**Instructions:**
Import the sha256 hash function from the Python hashlib library

Create a variable called difficulty and assign it a value of 2. This sets the number of leading zeros that the hash we find must have.

Create another variable called nonce and assign it to a value of 0. This will be our default starting value.

Using the .str() method, cast nonce and new_transactions into strings. Pass the two strings into the sha256 function.

Store the resulting hash value into a variable called proof and print it out!

Note: Use the .hexdigest() method over the resulting sha256 function to properly store the hash value.

Come up with some code that increments the nonce value until the generated hash has difficulty number of leading zeros. Once the desired proof has been found, store it in a variable called final_proof and print it out to see the correct hash!

**Solution:**
```python
new_transactions = [{'amount': '30', 'sender':'alice', 'receiver':'bob'},
               	{'amount': '55', 'sender':'bob', 'receiver':'alice'}]

# import sha256
from hashlib import sha256
# sets the amount of leading zeros that must be found in the hash produced by the nonce
difficulty = 2
nonce = 0

# creating the proof 
proof = sha256((str(nonce)+str(new_transactions)).encode()).hexdigest()
# printing proof
print(proof)
  
# finding a proof that has 2 leading zeros
while (proof[:2] != '0' * difficulty):
  nonce += 1
  proof = sha256((str(nonce) + str(new_transactions)).encode()).hexdigest()

# printing final proof that was found
final_proof = proof
print(final_proof)
```
