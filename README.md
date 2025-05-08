
# 🎮 Python Tic-Tac-Toe Game

This is a simple **Tic-Tac-Toe (X-O)** game made using Python.  
You can play it alone (against computer 🤖) or with a friend 👥 in the terminal.

---

## 🔧 How to Use

1. Run the program:
   ```bash
   python tictactoe.py
   ```

2. Choose game mode:
   - Press `1` for Single Player (You vs Computer)
   - Press `2` for Multiplayer (You vs Friend)

3. Enter position (1 to 9) to place X or O.

```
Positions:
1 | 2 | 3  
4 | 5 | 6  
7 | 8 | 9
```

---

## 🧠 What Each Function Does

| Function | What it does |
|----------|--------------|
| `ConstBoard()` | Shows the game board on screen |
| `User1Turn()` | Takes input for Player X |
| `User2Turn()` | Takes input for Player O |
| `minmax()` | Helps computer think and play smart |
| `CompTurn()` | Computer picks the best move |
| `analyzeboard()` | Checks who is winning |
| `main()` | Runs the game based on user choice |

---


# 🧠 How `minmax()` Works (In Simple Words)

The `minmax()` function is the **brain of the computer 🤖** in this Tic-Tac-Toe game.  
It helps the computer play smart — to **win** or **draw**, and avoid losing.

---

## 🧩 Step-by-Step Explanation

### 1. ✅ Check if someone already won
```python
x = analyzeboard(board)
if x != 0:
    return x * player
```

- If someone has already won:
  - Return `1` if computer wins ✅
  - Return `-1` if player wins ❌
  - Return `0` if it's a draw 🤝

---

### 2. 🔄 Try every empty spot
```python
for i in range(0, 9):
    if board[i] == 0:
        ...
```
Go through all 9 spots.  
If a spot is empty (`0`), try putting your move there.

---

### 3. 🧠 Think ahead using recursion
```python
board[i] = player
score = -minmax(board, player * -1)
board[i] = 0
```

- Place the move temporarily
- Call `minmax()` again for the **other player** (switch turns)
- The `-` sign flips the score because it's now the opponent's move
- Reset the move after checking

---

### 4. 🏆 Choose the best score
```python
if score > value:
    value = score
    pos = i
```

- Save the best score you find
- Remember which position gave that score

---

### 5. 📤 Return the best score
```python
return value
```

This tells how good the current move is.

---

## 🎯 In Short

- Computer tries all moves
- Thinks what will happen next
- Picks the move that avoids losing and tries to win

---

## 🏁 Game Result

At the end, the game will tell you:
- If it’s a **Draw** 🤝  
- If **Player X wins** ❌🏆  
- If **Player O wins** ⭕🏆  

---

Made for fun and learning 🎉  
Enjoy playing and feel free to improve it!
