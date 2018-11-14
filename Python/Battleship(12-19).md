**Battleship! Bad Aim<br>**

Great job! Now we can handle both correct and incorrect guesses from the user. But now let’s think a little bit more about the "miss" condition.

They can enter a guess that's off the board.
They can guess a spot they’ve already guessed.
They can just miss the ship.
We'll add these tests inside our else condition. Let's build the first case now!

if x not in range(8) or \
   y not in range(3):
  print "Outside the range"
The example above checks if either x or y are outside those ranges. The \ character just continues the if statement onto the next line.

**INSTRUCTIONS:**
Add a new if statement that is nested under the else.

Like the example above, it should check if guess_row is not in range(5) or guess_col is not in range(5).

If that is the case, print out "Oops, that's not even in the ocean."

After your new if statement, add an else that contains your existing handler for an incorrect guess. Don't forget to indent the code!

**MY CODE:**
```python
from random import randint

board = []

for x in range(0, 5):
  board.append(["O"] * 5)

def print_board(board):
  for row in board:
    print " ".join(row)

print_board(board)

def random_row(board):
  return randint(0, len(board) - 1)

def random_col(board):
  return randint(0, len(board[0]) - 1)

ship_row = random_row(board)
ship_col = random_col(board)
print ship_row
print ship_col

guess_row = int(raw_input("Guess Row: "))
guess_col = int(raw_input("Guess Col: "))

# Write your code below!
if guess_row == ship_row and guess_col == ship_col:
  print "Congratulations! You sank my battleship!"
elif guess_row not in range (5) or guess_col not in range (5):
  print "Oops, that's not even in the ocean."
else:
  print "You missed my battleship!"
  board[guess_row][guess_col] = "X"
  print_board(board)

  ```
