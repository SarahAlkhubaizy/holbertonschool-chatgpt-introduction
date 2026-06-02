# Holberton School - ChatGPT Introduction

## Debugging Directory

This directory contains code samples that were debugged and improved using ChatGPT.

---

## Tasks

### 0. Debugging - Python Factorial
**File:** `factorial.py`

**Objective:** Fix an infinite loop in the factorial function.

**Bug:** The `while` loop was not decrementing `n`, causing an infinite loop.

**Fix:** Added `n -= 1` inside the loop.

```python
#!/usr/bin/python3
import sys

def factorial(n):
    result = 1
    while n > 1:
        result *= n
        n -= 1
    return result

f = factorial(int(sys.argv[1]))
print(f)
```

**Usage:**
```bash
$ ./factorial.py 4
24
```

---

### 1. Debugging - Python Arguments
**File:** `print_arguments.py`

**Objective:** Fix the script to print only the arguments without the script name.

**Bug:** The loop started at index `0`, which includes `sys.argv[0]` (the script name).

**Fix:** Changed `range(len(sys.argv))` to `range(1, len(sys.argv))`.

```python
#!/usr/bin/python3
import sys

for i in range(1, len(sys.argv)):
    print(sys.argv[i])
```

**Usage:**
```bash
$ ./print_arguments.py 1 2 3
1
2
3
```

---

### 2. Debugging - HTML / Javascript
**File:** `change_background.html`

**Objective:** Fix the script to change the background color when clicking the button.

**Bug:** Typo in the button `id` — HTML had `id="colorButon"` while JavaScript referenced `id="colorButton"`.

**Fix:** Corrected the button `id` to `colorButton`.

```html
<button id="colorButton">Change Color</button>
```

---

### 3. Debugging - Python Mines
**File:** `mines.py`

**Objective:** Fix the Minesweeper game and add a win detection mechanism.

**Fix:** Added `is_won()` method to detect when all non-mine cells have been revealed, and called it after each successful reveal in `play()`.

```python
def is_won(self):
    for y in range(self.height):
        for x in range(self.width):
            if (y * self.width + x) not in self.mines and not self.revealed[y][x]:
                return False
    return True
```

**Usage:**
```bash
$ ./mines.py
...
Congratulations! You've won the game.
```

---

### 4. Documentation - Python Factorial
**File:** `factorial_recursive.py`

**Objective:** Add documentation to the recursive factorial function.

**Fix:** Added a docstring with three sections: function description, parameters, and returns. Also fixed indentation bug.

```python
#!/usr/bin/python3
import sys

def factorial(n):
    """
    Computes the factorial of a given number recursively.

    Parameters:
        n (int): A non-negative integer whose factorial is to be computed.

    Returns:
        int: The factorial of n. Returns 1 if n is 0.
    """
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

f = factorial(int(sys.argv[1]))
print(f)
```

**Usage:**
```bash
$ ./factorial_recursive.py 4
24
```

---

### 5. Error Handling - Python Checkbook
**File:** `checkbook.py`

**Objective:** Add error handling to prevent crashes on invalid input.

**Fixes:**
- Wrapped deposit and withdraw inputs in `try/except ValueError`
- Added validation to reject non-positive amounts

**Usage:**
```bash
$ ./checkbook.py
What would you like to do? (deposit, withdraw, balance, exit): deposit
Enter the amount to deposit: $test
Invalid input. Please enter a numeric value.
```

---

### 6. Debugging - Tic Tac Toe Python
**File:** `tic.py`

**Objective:** Identify and fix multiple errors in the Tic Tac Toe game.

**Bugs Fixed:**
- **Wrong winner displayed:** Player variable was swapped after a winning move, announcing the wrong winner.
- **No draw detection:** Added `is_draw()` to handle a full board with no winner.
- **No input validation:** Added `try/except` for non-numeric input and range checking for row/column values.

**Usage:**
```bash
$ ./tic.py
  |   |  
-----
Enter row (0, 1, or 2) for player X: 1
Enter column (0, 1, or 2) for player X: 1
...
Player X wins!
```

---

## Author
Sarah Alkhubaizy
