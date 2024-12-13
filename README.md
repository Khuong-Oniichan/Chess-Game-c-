# Chess Game in C++

Welcome to the **Chess Game** project! This game is built using **C++** and leverages the **SFML library** for graphical rendering. The project aims to provide a user-friendly interface and a functional chess-playing experience.

---

## Features

- **Interactive Gameplay**: Play chess against another player locally or against an AI.
- **Game Modes**:
  - **Player vs Player**: Two players can play on the same device, alternating turns.
  - **Player vs AI**: Play against a computer-controlled opponent with three difficulty levels:
    - **Easy**: The AI makes quick, random moves without strategy.
      - Selects a random piece and executes a valid move.
    - **Medium**: The AI uses the Minimax algorithm with Alpha-Beta Pruning at a depth of 2 moves per side.
      - Evaluates moves based on predefined piece values.
      - Adds position-specific evaluations (e.g., knights gain additional value when placed at the center of the board).
      - Sorts moves using the "Most Valuable Victim, Least Valuable Attacker" heuristic to prioritize efficient captures.
      - Uses bitboards (64-bit state representation) to optimize move generation and evaluation.
    - **Hard**: The AI uses the same approach as Medium but increases the Minimax depth to 3 moves per side for a more strategic play.
- **Visual Board Representation**: A graphical chessboard rendered using SFML, with features like piece dragging and move highlighting.
- **Rule Enforcement**: Implements all standard chess rules, including special moves like castling, en passant, and pawn promotion.
- **Move History**: Keeps track of moves in a log.
- **Customizable Settings**:
  - Board theme.
  - Piece design.
  - Sound effects for moves, check, and checkmate.
  - Background music with volume controls.
- **Save and Load Games**: Save the current game state to a file and reload it later to continue playing.
- **Undo/Redo Moves**: Allows players to undo or redo moves during gameplay.

---

## Installation

### Prerequisites

1. **C++ Compiler**: Ensure you have a C++14 (or higher) compatible compiler.
2. **SFML Library**: Download and install SFML 2.5.1 or later from [SFML's official website](https://www.sfml-dev.org/).

### Steps
#### Option 1: Run Pre-Built Executable
1. Locate the `chess.exe` file in the project folder.
2. Double-click the file to launch the game.

#### Option 2: Build from Source
1. **Setup SFML**: Ensure SFML is properly configured in your IDE (e.g., Code::Blocks or Visual Studio). Include the SFML headers and link the required libraries.
2. Open the project in your preferred IDE.
3. Build the project.
4. Run the generated executable from your IDE

## How to Play

1. Launch the game by running the executable.
2. A graphical chessboard will appear.
3. Choose a mode:
   - **Human vs Human**: Two players take turns making moves.
   - **Human vs BOT**: Choose AI difficulty (Easy, Medium, Hard), choose Black or White and play against the computer.
4. Use the graphical interface to:
   - Select and move pieces by clicking on them.
   - Highlight legal moves for the selected piece.
5. Additional options in the interface:
   - Start a new game.
   - Undo or redo the last move.
   - Save or load a game state.
   - Customize board theme, piece design, and sound effects.
6. The game ends when:
   - One player checkmates the other.
   - A stalemate or draw condition occurs.

---

## Project Structure

```
chess-game/
├── assets/               # Images, fonts, sound and game history
│   ├── images/           # images of pieces, boards, background and figure
│   ├── sound/            # Sound effects and music files
│   ├── fonts/            # fonts
│   ├── GameHistory/      # the saved game states
├── src/                  # Source code files
│   ├── main.cpp          # Entry point to manage overall game flow
│   ├── Menu.cpp          # Handles the main menu interface (Play, Settings, Exit)
│   ├── Mode.cpp          # Displays options for game modes (Player vs Player, Player vs AI)
│   ├── OnePlayerMode.cpp # Manages AI difficulty selection and player side (white or black)
│   ├── Playaswhite.cpp   # Handles game logic when the player is playing as white
│   ├── Playasblack.cpp   # Handles game logic when the player is playing as black
│   ├── Twoplayermode.cpp # Manages logic and interface for two-player games
│   ├── Settings.cpp      # Handles customization options for board, pieces, and sound effects
│   ├── SoundEffect.cpp   # Manages volume and settings for sound effects
│   ├── Backgroundmusic.cpp # Manages background music settings and volume
├── include/              # Header files
│   ├── Constant.h        # Constants and utility functions (e.g., `random`, `scalepicture`)
│   ├── Menu.h            # Definitions for the main menu interface
│   ├── Mode.h            # Definitions for game mode options
│   ├── OnePlayerMode.h   # Definitions for AI difficulty selection and player side
│   ├── Playaswhite.h     # Definitions for game logic when playing as white
│   ├── Playasblack.h     # Definitions for game logic when playing as black
│   ├── TwoPlayerMode.h   # Definitions for two-player game logic
│   ├── Settings.h        # Definitions for customization options
│   ├── SoundEffect.h     # Definitions for sound effect management
│   ├── Backgroundmusic.h # Definitions for background music management
├── README.md             # Project documentation
```

---

## Dependencies

- **SFML 2.5.1**: Used for rendering graphics and handling events.
- **Standard C++ Libraries**: For core functionality.

---

## Future Features

- **Multiplayer Online**: Enable online matches.
- **Enhanced Graphics**: Improve board and piece designs.
- **Piece Animations**: Add animations for smoother gameplay.
- **Fullscreen Support**: Implement the ability to resize or maximize the game window to fullscreen.
---

## Known Issues
- **Window size limitation**: Currently, the game does not support fullscreen mode and is constrained to the initial window size.
---

## Contribution

Contributions are welcome! 

## Contact

For questions or support, please reach out via:
- Email: phnam2409@apcs.fitus.edu.vn
- Email: dgkhuong2435@apcs.fitus.edu.vn
