BATTLESHIP!,br>
Play It, Sam

You can successfully make one guess in Battleship! But we’d like our game to allow the player to make up to 4 guesses before they lose.

for turn in range(4):
  # Make a guess
  # Test that guess
We can use a for loop to iterate through a range. Each iteration will be a turn.

**Instructions:**
Add a for loop that repeats the guessing and checking part of your game for 4 turns, like the example above.

At the beginning of each iteration, print "Turn", turn + 1 to let the player know what turn they are on.

Indent everything that should be repeated.

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
  else:
    print "You missed my battleship!"
    board[guess_row][guess_col] = "X"
  # Print (turn + 1) here!
  print_board(board)
  ```
