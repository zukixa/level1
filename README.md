## Project Overview

## Introduction

This project is designed to develop essential software engineering skills including API design, team collaboration, and multi-file development using a text-based maze game as the medium. The project focuses on the participation of multiple teams, each responsible for developing distinct components of the game. The primary goals are to reinforce understanding of cross-team integration, modular development, and implementation of comprehensive testing practices such as Test-Driven Development (TDD).

## Project Description

Teams will collaboratively write a text-graphics maze game. In this game, an adventurer represented by 'A' maneuvers through a maze filled with boulders ('\*') to reach a treasure ('T'). Each component of the game, from creating the maze to managing the game’s state, will be implemented in separate files by different teams.

## Emphasis Areas

1. **API Contracts Between Teams**:

   - Clear and precise API definitions are essential. Since each team works on separate modules, the interfaces between these modules must be well-defined. This ensures that the modules will integrate seamlessly despite being developed independently.

2. **Cross-Team Integration**:

   - After individual development, teams will need to integrate their component with others to assemble the complete game. This process will highlight the importance of maintaining communication and ensuring compatibility between different segments of code.

3. **Multi-File Development**:

   - To reinforce modular design principles, each team will work on separate files. This practice fosters better code organization and management, particularly in larger codebases.

4. **Test-Driven Development (TDD)**:
   - TDD will be employed to guide the software development process. Teams are expected to write tests before actual functional code, ensuring each component meets specified requirements and behaves as expected under various scenarios.

## Project Components

Teams will be tasked with developing several key functions of the game, each contained in its own folder and files:

- [`create_maze`:](https://github.com/zukixa/level1/tree/main/create-maze) Generates the maze structure.

  - **Inputs:**
    - `width`: Even integer number of characters for the maze’s width.
    - `height`: Even integer number of characters for the maze’s height.
    - `boulders`: Integer indicating the number of obstacles to randomly place in the maze.
  - **Output:**
    - `maze`: A `width` x `height` 2D array of characters with:
      - 'A' at `(0, 0)`.
      - 'T' at `(width-1, height-1)`.
      - '\*' asterisks representing boulders, randomly placed.
      - ' ' spaces placed everywhere else, representing "safe" spaces.

- [`print_maze`:](https://github.com/zukixa/level1/tree/main/print-maze) Handles the display of the maze and the number of remaining moves.

  - **Inputs:**

    - `width`: Even integer for the maze’s width.
    - `height`: Even integer for the maze’s height.
    - `maze`: `width` x `height` 2D array representing the maze, created in [`create_maze`](https://github.com/zukixa/level1/tree/main/create-maze#create-maze-function).
    - `moves_remaining`: Integer indicating how many moves the player has left.

  - **Output:**
    - Prints the maze using a fixed-width font to appear square, alongside the move count.

- [`get_move`:](https://github.com/zukixa/level1/tree/main/get-move) Captures player's input for movement.

  - **Inputs:**
    - Prompt the player for a move: 'U' (up), 'D' (down), 'L' (left), 'R' (right).
  - **Outputs:**
    - `delta_x`: Integer equal to -1, 0, or 1 indicating the change in horizontal position.
    - `delta_y`: Integer equal to -1, 0, or 1 indicating the change in vertical position.

- [`check_move`:](https://github.com/zukixa/level1/tree/main/check-move) Validates the player's movement based on the game rules.

  - **Inputs:**
    - `current_x`: Integer indicating the player's current horizontal position.
    - `current_y`: Integer indicating the player's current vertical position.
    - `width`: Even integer representing the maze's width in characters.
    - `height`: Even integer representing the maze's height in characters.
    - `maze`: `width` x `height` 2D array representing the maze, created in [`create_maze`](https://github.com/zukixa/level1/tree/main/create-maze#create-maze-function).
    - `delta_x`: Integer (-1, 0, or 1) representing the change in horizontal position.
    - `delta_y`: Integer (-1, 0, or 1) representing the change in vertical position.
  - **Outputs:**
    - `bad`: Boolean indicating if the move places the player outside the maze or on a boulder.
    - `won`: Boolean indicating if the move places the player at the treasure.

- [`update_maze`:](https://github.com/zukixa/level1/tree/main/update-maze) Updates the maze and player's position based on the movement.

  - **Inputs:**
    - `current_x`: Integer for the player's current horizontal position.
    - `current_y`: Integer for the player's current vertical position.
    - `maze`: `width` x `height` 2D array representing the maze, created in [`create_maze`](https://github.com/zukixa/level1/tree/main/create-maze#create-maze-function).
    - `delta_x`: Integer indicating the change in horizontal position.
    - `delta_y`: Integer indicating the change in vertical position.
  - **Outputs:**
    - `current_x`: Updated horizontal position.
    - `current_y`: Updated vertical position.
    - `maze`: Updated `width` x `height` 2D array reflecting the new player's and potentially treasure's positions.

- [`display_banner`:](https://github.com/zukixa/level1/tree/main/display-banner) Displays messages based on game outcomes (win/loss).
  - **Inputs:**
    - `bad`: A boolean value indicating if a move places the player outside the maze or on a boulder.
    - `won`: A boolean value indicating whether the player has won (True) or lost (False).
  - **Output:**
    - Print some form of bad move message if `bad` is True.
    - Print a celebratory message if `bad` is False and `won` is True.
    - Print a disappointing message of sorts if `bad` is False and `won` is False.

Each folder holds further instructions on how to implement and work on your team's subsection.

## Development Strategy

- **Modular Development**: Each team works on a separate piece; modules should be designed to be self-contained and independently functional.
- **Collaboration and Version Control**: Git will be used to manage changes. Teams should create feature branches for development before merging into the main branch, enabling a controlled integration process and familiarization with common source control workflows, including handling merge conflicts.
- **Integration and Testing**: Post-development, integration testing across the different modules will be critical to ensure the game functions as a whole. Teams are encouraged to engage in both manual and automated testing.

## Conclusion

This project is not just about coding but understanding how to work as part of a software development team. The structured approach will enhance your ability to design, implement, and integrate software components effectively, a key skill in any software developer's toolkit.
