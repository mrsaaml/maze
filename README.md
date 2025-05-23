

 Maze Generator and Solver 

1. Overview
This Java program generates a random maze using a recursive backtracking algorithm and then solves it using a depth-first search (DFS) approach. The maze is represented as a 2D grid where:
- `1` represents a wall (`#`).
- `0` represents a path (empty space).
- `S` marks the start position.
- `E` marks the exit position.
- `.` shows the solution path.

2. Features

2.1 Maze Generation
- Recursive Backtracking Algorithm 
  - The maze is generated by recursively carving out paths from the starting position.
  - The algorithm works by:
    1. Starting at a given cell and marking it as a path (`0`).
    2. Randomly shuffling directions (up, right, down, left) to ensure randomness.
    3. Moving two cells in each direction and carving through walls if the next cell is valid (within bounds and still a wall).
  - This ensures a perfect maze (no loops, only one solution).

- Start and Exit Points 
  - The start (`S`) is fixed at `(1, 1)` (top-left area).
  - The exit (`E`) is fixed at `(rows-2, cols-2)` (bottom-right area).
  - Ensures these points are always open.

- Connectivity Check  
  - After generation, a DFS (Depth-First Search) checks if the exit is reachable.
  - If not, it manually connects the exit to the nearest path.

2.2 Maze Solving
- Depth-First Search (DFS) Solver  
  - The solver uses recursion to explore possible paths:
    1. Marks the current cell as visited.
    2. Checks if the exit is reached.
    3. Explores all four directions (up, right, down, left).
    4. Backtracks if a dead end is encountered.
  - The solution path is stored in a list (`path`) and displayed with dots (`.`).

2.3 Visualization
- Console-Based Printing  
  - The maze is printed in a readable format:
    - `#` → Wall
    - ` ` (space) → Open path
    - `S` → Start
    - `E` → Exit
    - `.` → Solution path (if solved)

2.4 Helper Classes & Methods
- `Cell` Class  
  - Represents a cell with `(row, col)` coordinates.
  - Overrides `equals()` and `hashCode()` for proper comparison in collections.
  
- Direction Handling 
  - Uses predefined direction offsets (`{{-1, 0}, {0, 1}, {1, 0}, {0, -1}}`) for movement.

3. Example Execution
  
3.1 Maze Generation 
   - A `15x15` maze is created.
   - Walls and paths are randomly generated.
   - Ensures start and exit are connected.

3.2 Maze Solving  
   - DFS finds a path from `S` to `E`.
   - The solution is printed with dots (`.`).

3.3 Output  
   - First, the unsolved maze is displayed.
   - Then, the solved maze is shown with the path.

