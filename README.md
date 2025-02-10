# Treasure Hunt Game - AP CSA Project

## Overview
In this project, you will create a **Treasure Hunt Game** using a **2D array of objects**. The player navigates a grid to find **hidden treasures** while avoiding **traps**.

The game will track the player’s progress by revealing explored locations while keeping unexplored spaces hidden. The player wins by finding **all the treasures** or loses if they hit **too many traps**.

---

## Requirements
Your game must:
- ✅ Use a **2D array** to represent the game board.
- ✅ Have at least **two classes** (`Cell` and `TreasureMap`).
- ✅ Allow the **player to move** using keyboard input (`up`, `down`, `left`, `right`).
- ✅ Reveal **treasures (T)** and **traps (X)** when stepped on.
- ✅ Keep unexplored locations **hidden (-)** until the player reveals them.
- ✅ Track **wins/losses** based on treasures found and traps hit.
- ✅ Display the **grid** after each move.

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
public boolean isGameOver() // Ends game if player finds all treasures or loses all lives
public void displayMap() // Prints the grid
```

---

## Step 3: The `TreasureHuntGame` Class
This class will run the game loop.

### Instance Variables
```java
private TreasureMap map;
private int treasureFound; // Number of treasures collected
private int livesRemaining; // Number of lives left (start with 3)
```

### Methods
```java
public void playGame() // Runs game loop
public void displayInstructions() // Prints how to play
public void displayResult() // Shows win/lose message
```

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

## Step 5: Bonus Features (For Extra Challenge)
- **Hint System:** Show how many treasures are nearby.
- **Limited Moves:** Player must find treasure within `X` moves.
- **Larger Grid:** 10×10 or customizable size.
- **Multiple Players:** Allow two players to take turns.

---

## Submission & Grading
✅ **Code must be well-documented** (comments for each method).  
✅ **Proper use of 2D arrays** (`Cell[][]`).  
✅ **Game must run without errors**.  
✅ **Creative extras will earn bonus points**! 🎉  

---

### Would this work for your students? Let me know if you need tweaks! 🚀
