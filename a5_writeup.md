# Assignment 5 Write up

Assignment 5 can be broken up into the following parts:
1. Import the Necessary Modules:
- `copy`: For creating deep copies of objects
- `Stack` and `Queue`: Custom implementations for DFS and BFS operations
2. Utility Functions: 
- `remove_if_exists`: Removes a specified element from a list if it exists, which is used to remove the possibilites from a cell
3. Board Class:
- Represents the Sudoku board
- Consists of functions that will find the most constrained cell, and update the board, which eliminates possible solutions
4. DFS & BFS Functions:
- `DFS`: Uses depth-first search to solve the Sudoku puzzle. It works by trying to fill the most constrained cell with potential values until a solution is found or backtracks if a mistake is made
- `BFS`: Uses breadth-first search to solve the Sudoku puzzle in a similar fashion to DFS but explores nodes level by level
5. Main Execution:
- Defines two different sets of initial moves for Sudoku puzzles
- Uses both DFS and BFS to solve each puzzle and prints the results


After completing the assignment, answer the following reflection questions:

## Reflection Questions

1. How do the performance and efficiency of the Depth-First Search (DFS) and Breadth-First Search (BFS) algorithms compare when solving Sudoku puzzles? In what scenarios might one approach be preferable over the other?

I think that the DFS is faster than the BFS in this case, since the BFS is just going to do more work than DFS in every scenario. There is a possibility for some sudoku boards where the DFS and BFS will end up going through different paths because the BFS found a shorter one than what the DFS took, but I think it would still solve it slower than the DFS because it probably had to go through most actions of the other paths anyway. It is probably possible though for BFS to be faster than DFS if one of the paths is way faster than the one that DFS chooses to go on.


2. How did the choice of data structures (like the Stack for DFS and Queue for BFS) impact the implementation and functionality of the algorithms? Are there alternative data structures or design patterns that could have been used to achieve the same objectives?

The choice of data structures impacted the implmentation and funcionality of the algorithms becahse they allowed for each one to work in their unique way. The codes were increadibly similar for both algorithms, yet pretty much just changing the type of data structure was enough to make the two completely different algorithms. I know for a fact that for depth first search, something like a list could work, although I think it would be slower.

3. Considering the current implementation, how might the Sudoku solver be adapted or extended for larger puzzles or different types of grid-based logic games? How can the lessons learned from this assignment be applied to real-world problem-solving or optimization challenges?

The way we created a sudoku solver was by narrowing down the number of possibilities, and then going through each one. This can be applied to many problems/puzzles. A very important part of our solver was using the heuristic of finding the least constrained cell, since that actually speeds up the program a lot in many of the situations. This heuristic added some program complexity, which in a few cases(like an solving an empty sudoku board) could make the program slower, but in the vast majority of cases, expecially where the program starts to take a long time, the heuristic is actually very efficient and reduces the time the solver takes by a ton. The main reason the heuristic works so well is because it minimizes the x in the (a)x^n complexity, which on the scale of n being up to 81, reducing x with the cost of increasing a is worth it a lot of theb time.