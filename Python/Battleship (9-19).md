BATTLESHIP!
It's Not Cheating—It's Debugging!<br>

Awesome! Now we have a hidden battleship and a guess from our player. In the next few steps, we'll check the user's guess to see if they are correct.

While we're writing and debugging this part of the program, it will be helpful to know where that battleship is hidden. Let's add a print statement that displays the location of the hidden ship.

Of course, we'll remove this output when we're finished debugging since if we left it in, our game wouldn't be very challenging. :)

**Instructions:**
Before the lines prompting the user for input:

Print the value of ship_row.

Print the value of ship_col.

**MY CODE:**
```python
from random import randint

board = []

for x in range(0, 5):
  board.append(["O"] * 5)

def print_board(board):
  for row in board:
    print " ".join(row)

def random_row(board):
  return randint(0, len(board) - 1)

def random_col(board):
  return randint(0, len(board[0]) - 1)

ship_row = random_row(board)
ship_col = random_col(board)
# Add your code below!

guess_row = int(raw_input("Guess Row: "))
guess_col = int(raw_input("Guess Col: "))

print ship_row
print ship_col
```
