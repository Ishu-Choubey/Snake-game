# Snake-game
Snake game using C++
Explaination of code:

1. **Initialization and Global Variables**:
   - The code begins by including necessary header files like `<iostream>`, `<conio.h>`, `<windows.h>`, and `<time.h>`. These are used for console I/O, keyboard input, timing, and some Windows-specific functions.
   - It defines several global variables and arrays to store the game state, including the position of the snake (head and tail), the position of the fruit, the game score, and the direction of movement (`eDirection` enum).

2. **Setup Function**:
   - The `Setup` function initializes the game's initial state.
   - It sets `gameOver` to `false`, places the snake in the middle of the game board, and generates the initial fruit position using `rand()` seeded with the current time.
   - The `score` is set to zero.

3. **Draw Function**:
   - The `Draw` function is responsible for rendering the game on the console.
   - It clears the console with `system("cls")` and then iterates through the game board's cells, printing the snake's head as 'O,' the fruit as 'F,' and the snake's tail as 'o.' Empty cells are printed as spaces.
   - The score is displayed at the bottom of the screen.

4. **Input Function**:
   - The `Input` function checks for keyboard input using `_kbhit()` and `_getch()`. 
   - Depending on the key pressed ('a' for left, 'd' for right, 'w' for up, 's' for down, 'x' for exit), it updates the direction in which the snake will move.

5. **Logic Function**:
   - The `Logic` function handles the game's logic and mechanics.
   - It updates the position of the snake's head based on the current direction.
   - If the snake goes out of bounds (hits the wall), it sets `gameOver` to true.
   - It checks if the snake collides with its own tail, which also ends the game.
   - If the snake's head collides with the fruit, the score is increased, and a new random position for the fruit is generated.
   - The snake's tail is updated to follow the head's previous positions.

6. **Main Function**:
   - In the `main` function, the console window size is set to 24 columns and 25 lines using the `system("MODE con cols=24 lines=25")` command.
   - The game loop runs until `gameOver` is true.
   - Inside the loop, `Draw`, `Input`, and `Logic` functions are called repeatedly.
   - `Sleep(50)` introduces a small delay (in milliseconds) between frames to control the game's speed.

The code creates a basic console-based Snake game with a main loop that continuously updates the game state, takes user input, and renders the game. Players control the snake to collect fruit and score points while avoiding collisions with the wall and the snake's tail.
