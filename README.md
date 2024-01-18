# GameBot API Implementation 

## I. Prerequisites and Dependencies

### Operating System
- Windows 7 or above (64-bit)

### Python API Details
- Implemented in Python 3.6.3
- Tested for Python version 3 and above
- Slight changes required for versions below 3

### BizHawk Emulator
- Install prerequisites from the attached zip file

## II. Running the Game and Executing API Code

### 1. Single Bot (Your Bot vs CPU)
- Open the "single-player" folder.
- Run EmuHawk.exe.
- Open ROM: Street Fighter II Turbo (U).smc.
- Open Tool Box: Tools > Tool Box (Shift+T).
- Open command prompt in the API directory.
- Run: `python controller.py 1`

### 2. Two Bots (Both Fighting Each Other)
- Open the "two-players" folder.
- Repeat steps 2-6 for both players (1 and 2).

### 3. Selecting Characters
- Choose characters after selecting normal mode.
- Set controls from the emulator's config drop-down.

### 4. Establishing Connection
- Click on the Gyroscope Bot icon (second icon) to connect.
- Terminal shows "Connected to the game!" or "CONNECTED SUCCESSFULLY."

### 5. Code Execution
- Program stops after a single round.
- Repeat the process for subsequent rounds.

## III. API Details

### Buttons Class
- Represents SNES gamepad buttons.
- 12 boolean members representing each button.

### Player Class
- Represents a player in the game.
- Data members:
  - player_id, health, x_coord, y_coord, is_jumping, is_crouching, player_buttons, in_move, move_id.

### GameState Class
- Represents information from the game at a time instance.
- Data members:
  - player1, player2 (Player objects)
  - timer, fight_result, has_round_started, is_round_over.

### Command Class
- Represents the command passed to the game.
- Contains Buttons objects for the respective player.

### Controller Class
- Contains socket connection logic, communication logic, and the main game loop.

## IV. Implementation Task

### Fight Function
- Implement the fight function in bot.py or Bot.java.
- Takes GameState object and player string as input.
- Use GameState information to set buttons in the Command object.
- Return the Command object from the function.

### Dataset Generation
- Generate a dataset by playing single player.
- Record all percepts and actions in a CSV format.
- Dataset required for ML/DL algorithm training.

### Solution Requirements
- Solution must be generic; player chosen randomly.
- Reinforcement learning/rule-based agents not allowed.
