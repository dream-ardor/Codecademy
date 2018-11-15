BATTLESHIP!<br>
Game Over

If someone runs out of guesses without winning right now, the game just exits. It would be nice to let them know why.

Since we only want this message to display if the user guesses wrong on their last turn, we need to think carefully about where to put it.

We’ll want to put it under the else that accounts for misses
We’ll want to print the message no matter what the cause of the miss
Since our turn variable starts at 0 and goes to 3, we will want to end the game when turn equals 3.


**Instructions:**
Add an if statement that checks to see if the user is out of guesses.

Put it under the else that accounts for misses.
Put it after the if/elif/else statements that check for the reason the player missed. We want "Game Over" to print regardless of the reason.
If turn equals 3, print "Game Over".

**MY CODE:**
```python
from random import randint

board = []

for x in range(5):
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

# Everything from here on should go in your for loop!
for turn in range(4):
  print "Turn", turn + 1
# Be sure to indent four spaces!
guess_row = int(raw_input("Guess Row: "))
guess_col = int(raw_input("Guess Col: "))

if guess_row == ship_row and guess_col == ship_col:
  print "Congratulations! You sunk my battleship!"
else:
  if (guess_row < 0 or guess_row > 4) or (guess_col < 0 or guess_col > 4):
    print "Oops, that's not even in the ocean."
  elif(board[guess_row][guess_col] == "X"):
    print "You guessed that one already."
  elif turn == 3:
    print "Game Over"
  else:
    print "You missed my battleship!"
    board[guess_row][guess_col] = "X"
  # Print (turn + 1) here!
  print_board(board)
  ```

  
