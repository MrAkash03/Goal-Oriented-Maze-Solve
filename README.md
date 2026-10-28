Goal-Conditioned Maze Solver using Q-Learning
A reinforcement learning project that trains a Q-Learning agent to navigate grid-based mazes with dynamic start positions, dynamic goal positions, and multiple maze layouts.

Project Overview
This project explores how reinforcement learning agents learn navigation tasks in increasingly complex environments.

The agent is trained using Q-Learning and is progressively challenged with:

Fixed start and goal positions
Random start positions
Random goal positions
Multiple maze layouts
The project demonstrates how state representation affects learning performance and generalization.

Features
✅ Q-Learning implementation from scratch

✅ Dynamic start positions

✅ Dynamic goal positions

✅ Multiple maze layouts

✅ Route visualization

✅ Training reward visualization

✅ Success rate evaluation

✅ Goal-conditioned state representation

Environment
Maze Representation
0 = Empty Cell
1 = Wall
Example Maze:

S . . . .
X X . X .
. . . X .
. X . . .
. . . X G
Where:

S = Start Position
G = Goal Position
X = Wall
. = Valid Path
Actions
The agent can perform four actions:

0 = Up
1 = Down
2 = Left
3 = Right

Reward Function
Reach Goal      +100

Hit Wall        -10

Leave Grid      -10

Valid Move      -1
The reward structure encourages the agent to find the shortest valid path to the goal.
______________________________________
Learning Progression:

Phase 1
Fixed Start

Fixed Goal

Fixed Maze

Result:
        Success Rate ≈ 95-100%
____________________________________
Phase 2
Random Start

Fixed Goal

Fixed Maze

Result:
        Success Rate > 90%
______________________________________
Phase 3
Random Start

Random Goal

Fixed Maze

Initial Attempt
State: (row, col)

Result:
        Success Rate ≈ 11%

Issue: The agent did not know the goal location.

Solution: Expanded state representation:

(
  current_row,
  current_col,
  goal_row,
  goal_col
)
Result:
        Success Rate > 90%
___________________________       
Phase 4
Random Start

Random Goal

Multiple Maze Layouts

Result:
        Success Rate ≈ 51%
__________________________
Observation:

The agent generalizes partially across multiple maze structures but cannot fully distinguish maze layouts because maze configuration is not included in the state representation.

Technologies Used
Python
NumPy
Matplotlib
Q-Learning
Google Colab
___________________________
Results
Phase	Environment	Success Rate
Phase 1	Fixed Start + Fixed Goal	~95-100%
Phase 2	Random Start	>90%
Phase 3 (Before Fix)	Random Goal	~11%
Phase 3 (After Fix)	Goal-Aware State	>90%
Phase 4	Multiple Mazes	~51%
_______________________________
Key Learnings
State representation is critical in reinforcement learning.
A policy that works in one environment may fail to generalize.
Goal information must be included when solving dynamic navigation tasks.
Increasing environment complexity can significantly reduce performance without additional state information
__________________________________
Future Improvements
Random maze generation
Variable maze sizes
Gymnasium environment wrapper
Deep Q Network (DQN)
PPO implementation
Maze-aware state representation
Curriculum learning
