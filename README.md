1. Introduction:
The FourInARow program is a Java-based graphical user interface (GUI) application designed to simulate the classic two-player game "Connect Four." The game allows players to alternate turns, dropping colored discs into a grid, aiming to get four in a row horizontally, vertically, or diagonally. The program uses Java Swing components to create the game interface and manage user interactions.

2. Program Structure:
The program is organized into two main classes:

Class FourInARow:

This is the main class responsible for initializing the game window (JFrame) and setting up the game board by adding an instance of the inner multi class.
Inner Class multi:

This class extends JPanel and implements MouseListener, managing the game board, user interactions, and game logic.
3. Components and Functionality:
Graphical User Interface (GUI):

The JFrame (game window) is set up with a size of 600x400 pixels, with a title "FourInARow."
The multi class is responsible for drawing the grid, handling mouse clicks, and managing the game state.
The game board consists of a 6-row by 7-column grid, each cell represented as a circle (fillOval), initially colored white.
Game Logic:

Turn Management:
The game alternates between two players (Red and Yellow), tracked by the turn variable. The player's turn is displayed in the top right corner.
Disc Dropping Mechanism:
When a player clicks on a column, the program determines the lowest available row in that column using the dropP method. The disc is then "dropped" (colored) in that position.
Winner Detection:
After each move, the program checks for a winner using the checkForWinner method. This method examines all possible directions (horizontal, vertical, and diagonal) from the last placed disc to see if there are four consecutive discs of the same color.
Reset Mechanism:
The game can be reset by the reset method, which clears the grid and resets the turn counter and winner status.
Event Handling:

Mouse Events:
The program uses the MouseListener interface to handle mouse clicks. The mousePressed method captures the player's click, determines the appropriate column and row, and updates the game state accordingly.
Drawing:
The paintComponent method is overridden to draw the game board. It refreshes the display after each move, showing the current state of the grid and any messages (e.g., indicating the winner).
Key Methods:

dropP(int cc):
Determines the lowest available row in the clicked column where the disc can be placed.
checkForWinner(int cc, int cr, Color c):
Checks if the current move results in a win by looking for four consecutive discs of the same color in any direction.
reset():
Resets the game to its initial state, clearing the grid and setting the game up for a new round.
4. Workflow:
Initialization:

The game window is initialized by the FourInARow constructor. The multi class is instantiated with the window's dimensions and is added to the frame.
Gameplay:

Players alternate clicking on the columns where they want to drop their disc. The game board updates with each move, and the program checks for a winner after each turn.
End Game:

If a player successfully aligns four discs in a row, the game announces the winner and prevents further moves until the game is reset.
5. Limitations:
Game Reset:

The game automatically resets when the mouse exits the game window, which might be unintuitive for players expecting a manual reset button or an in-game prompt.
Edge Cases:

The program does not handle cases where the grid becomes full without a winner, resulting in a draw. Additional logic could be added to manage such scenarios.
User Feedback:

The game does not provide user feedback for invalid moves (e.g., clicking on a full column). Implementing this feature could enhance the user experience.
GUI Scaling:

The GUI is fixed in size, and the game board does not dynamically scale with the window, limiting flexibility on different screen sizes.
6. Conclusion:
The FourInARow program provides a functional and interactive implementation of the classic Connect Four game. It serves as an educational example of handling user input, graphical rendering, and basic game logic in Java using Swing. While the program is functional, there are opportunities for enhancement, such as improved user feedback, better handling of edge cases, and more intuitive reset mechanisms.
