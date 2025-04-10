# Monopoly Game
**Created by: Aseel Ahmad**

## Overview
This project is a Monopoly game implementation in C++ for Ubuntu 22.04 LTS. It features:
- Player management
- Game board logic
- Property purchasing
- Rent payments
- Several other core Monopoly mechanics

Both **clang++** and **g++** compilers are supported, and test cases (using doctest) are provided to validate game functionality.

---

## Development Environment
- **Operating System:** Ubuntu 22.04 LTS
- **Compilers:**  
  - clang++ version 14  
  - g++ version 11
- **Testing Framework:** doctest (included in the project)

---

## Build and Run Instructions
Open a terminal in the project directory and use the following `make` commands:

1. **Build and run the game (clang++):**
   ```bash
   make
   ```
   This compiles the game using clang++ and starts the Monopoly game.

2. **Build and run test cases (clang++):**
   ```bash
   make test
   ```
   This compiles and runs the test suite (unit tests) using doctest.h with clang++.

3. **Build and run the game (g++):**
   ```bash
   make g++
   ```
   This compiles the game using g++ and starts the Monopoly game.

4. **Build and run test cases (g++):**
   ```bash
   make testg++
   ```
   This compiles and runs the test suite (unit tests) using doctest.h with g++.

---

## Recommended Screen Resolution
- **Best Experience:** Full HD (1920×1080)  
- **Supported:** HD (1360×768) and other resolutions  
- **Note:** Full HD is recommended for optimal visual clarity.

---

## Game Rules

### Rent Fees for Properties
| Houses/Hotels | Rent Fee (Percentage of Street Price) |
|---------------|---------------------------------------|
| 0 Houses      | 10%                                   |
| 1 House       | 20%                                   |
| 2 Houses      | 40%                                   |
| 3 Houses      | 80%                                   |
| 4 Houses      | 160%                                  |
| Hotel         | 320%                                  |

### Upgrade/Build Costs
- **Each House:** 50% of the property's initial price  
- **Hotel:** Cost of 4 houses **plus** ₪100

### Property Sale Price
When selling properties, the sale price is always **50% of the purchase price**, which applies to:
- Streets
- Companies
- Railroads
- Houses and hotels

### Chance Cards
Sample Chance cards:
- Advance to Go: Collect ₪200
- Bank pays you dividend: Collect ₪50
- Go back 3 spaces
- Go directly to Jail: Do not pass Go, do not collect ₪200
- Pay poor tax: ₪15
- Advance to nearest Utility or Railroad: If owned, pay rent; otherwise, buy it from the bank

### Community Chest
Sample Community Chest cards:
- Bank error in your favor: Collect ₪200
- Income tax refund: Collect ₪20
- You inherit: ₪100
- Life insurance matures: Collect ₪100

---

## Class and File Descriptions

### `Definitions.hpp`
Contains essential definitions and constants used throughout the game.
- **Key Features:**
  - Constants for maximum players
  - Enumerations for cell types and game states
  - A `Helper` class for utility functions
- **Importance:**
  - Central reference for common terms
  - Makes adjusting definitions across the program simpler

### `GameCell` Class
Represents a single space on the Monopoly board.
- **Key Features:**
  - Stores cell type (e.g., street, railroad, chance)
  - Tracks ownership of properties
  - Manages visual representation of the board cell
- **Importance:**
  - Core building block of the board
  - Governs space-specific rules and updates the display

### `Player` Class
Manages individual player data and actions.
- **Key Features:**
  - Stores player name, money, position, and jail status
  - Manages "Get Out of Jail Free" cards
- **Importance:**
  - Represents each player in the game
  - Tracks critical player status data

### `GameBoard` Class
Manages the overall game.
- **Key Features:**
  - Contains all `GameCell` and `Player` objects
  - Keeps track of game states and player actions
  - Logs game events
- **Importance:**
  - Central controller that enforces rules
  - Oversees all aspects of gameplay

### `GameWindow` Class
Handles the graphical user interface (GUI) and user input.
- **Key Features:**
  - Creates and manages the game window size
  - Draws the board, players, and other visual elements
  - Processes user input and updates the display
- **Importance:**
  - Provides all visual representation
  - Interface for user interaction

### `Monopoly.cpp` (Main Game Logic)
Entry point and main loop of the game.
- **Key Features:**
  - Initializes the game window
  - Runs the main game loop
- **Importance:**
  - Launches the game
  - Updates state and redraws until the game ends

### Test Cases (`TestMonopoly.cpp`)
Unit tests to ensure correct game behavior.
- **Key Features:**
  - Uses the doctest framework
  - Covers various game scenarios
- **Importance:**
  - Maintains game reliability
  - Ensures rules and logic are correctly implemented
