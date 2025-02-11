# Treasure Hunt Game - AP CSA Project

## Overview
This project will be worth the same as an exam.  Therefore, it is expected that you do this project without AI assistance.  Evidence of AI assistance will result in stiff penalties.
Frequent random check-ins by the instructor will require you to explain your progress to that point.  Failure to be able to explain or failure to have ample progress will result in a deduction.

In this project, you will create a **Treasure Hunt Game** using a **2D array of objects**. The player navigates a grid to find **hidden treasures** while avoiding **traps**.

The game will track the player’s progress by revealing explored locations while keeping unexplored spaces hidden. The player wins by finding **all the treasures** or loses if they hit **too many traps**. If the **Limited Moves** bonus feature is enabled, the player may also lose by running out of moves.

---

## Requirements
Your game must:
- ✅ Use a **2D array** to represent the game board.
- ✅ Have at least **two classes** (`Cell` and `TreasureMap`). The `TreasureHuntGame` class is suggested to manage the game loop, but students may structure their implementation differently as long as gameplay functions correctly.
- ✅ Allow the **player to move** using keyboard input (`up`, `down`, `left`, `right`).
- ✅ Reveal **treasures (T)** and **traps (X)** when stepped on.
- ✅ Keep unexplored locations **hidden (-)** until the player reveals them.
- ✅ Track **wins/losses** based on treasures found, traps hit, and moves remaining.
- ✅ Display the **grid** after each move.
- ✅ Ensure that previously visited spaces remain revealed and can be revisited without any additional effects.
- ✅ Handle all error exceptions, including incorrect direction input, movement out of bounds, and any unexpected user input.
- ✅ Allow the player to **customize the grid size** and define the **number of treasures and traps** at the start of the game.

---

## Step 1: The `Cell` Class
Each cell in the grid will be represented by a `Cell` object.

### Instance Variables
```java
private boolean hasTreasure; // True if treasure is in this cell
private boolean hasTrap; // True if a trap is in this cell
private boolean isRevealed; // True if the player has already stepped on this cell
```

### Methods
```java
public Cell(boolean hasTreasure, boolean hasTrap) // Constructor
public void reveal() // Marks the cell as revealed
public boolean hasTreasure() // Returns true if this cell has treasure
public boolean hasTrap() // Returns true if this cell has a trap
public boolean isRevealed() // Returns true if the cell is revealed
```

---

## Step 2: The `TreasureMap` Class
The `TreasureMap` class will manage the **2D grid of `Cell` objects**.

### Instance Variables
```java
private Cell[][] grid; // The 2D array that stores the game board
private int playerRow, playerCol; // Player’s current location
```

### Methods
```java
public TreasureMap(int rows, int cols, int numTreasures, int numTraps) // Constructor
public void movePlayer(String direction) // Moves player and checks for treasure/traps
public boolean isGameOver() // Ends game if player finds all treasures, loses all lives, or runs out of moves
public void displayMap() // Prints the grid
```

### Player Starting Position and Movement Rules
- The player will be prompted to **input the grid size** (number of rows and columns) at the start of the game.
- The player will also **choose the number of treasures and traps** to be randomly placed on the board.
- The player’s starting position will be randomly assigned to an empty space that does not contain a treasure or a trap.
- When the player moves to a new space, it is automatically revealed.
- If the player revisits a previously explored space, nothing changes; the space remains revealed and does not trigger additional effects.
- The game should handle all invalid movement attempts, such as moving out of bounds or entering an incorrect command.

---

## Step 3: The `TreasureHuntGame` Class
This class will run the game loop.  (How you run the game loop is up to you.  This is just one possible way.)

### Instance Variables
```java
private TreasureMap map;
private int treasureFound; // Number of treasures collected
private int livesRemaining; // Number of lives left (start with 3)
private int movesRemaining; // Number of moves left before game over
```

### Methods
```java
public void playGame() // Runs game loop
public void displayInstructions() // Prints how to play
public void displayResult() // Shows win/lose message
```

### Game Over Conditions
The game will end when:
- **Win Condition:** The player collects all treasures.
- **Lose Conditions:**
  - The player steps on too many traps and loses all lives.
  - The player runs out of moves before collecting all treasures (only if the Limited Moves bonus feature is enabled).
- The `displayResult()` method should print an appropriate message based on the outcome.

### Error Handling Requirements
- Ensure the game does not crash due to invalid user input.
- If the user enters an invalid direction, prompt them to re-enter.
- If the user attempts to move out of bounds, display a message and allow them to retry.
- If the user inputs an invalid grid size or number of treasures/traps, prompt them to enter a valid number.
- Handle any unexpected input gracefully.

---

## Step 4: Example Gameplay

### Initial Grid (Hidden Cells)
```
-  -  -  -  -  
-  -  -  -  -  
-  -  P  -  -  
-  -  -  -  -  
-  -  -  -  -  
```

### After Moving Right (`right`)
```
-  -  -  -  -  
-  -  -  -  -  
-  -  .  P  -  
-  -  -  -  -  
-  -  -  -  -  
```

### After Finding Treasure
```
-  -  -  -  -  
-  -  -  -  -  
-  -  T  P  -  
-  -  -  -  -  
-  -  -  -  -  
```

### After Hitting a Trap
```
-  -  -  -  -  
-  -  -  -  -  
-  -  X  P  -  
-  -  -  -  -  
-  -  -  -  -  
```

---

## Step 5: Bonus Feature
- **Limited Moves:** Player must find all treasures within a specified number of moves.

---

## Submission & Grading
✅ **Game must be user-friendly.  That is, all instructions to the user must be clear as to what is expected of them and how to play the game.**     
✅ **Code must be well-documented** (comments of all types: line comments, block comments, documentation comments, clarification comments).  
✅ **Proper use of 2D arrays** (`Cell[][]`).  
✅ **Final version of the game must run without errors**.  Be sure to error test all possible issues.   
✅ **Frequent check-ins by the instructor will require you to explain your code at different stages in the development of the project.**  
      Failure to do so or to have ample progress will result in a 5% deduction for each check-in.  
✅ **Code will be tested by classmates in addition to your instructor.**   
      Failure to have your code completed on the specified day of testing will result in a 15% deduction.   
✅ **Creative extras will earn bonus points**! 🎉   


