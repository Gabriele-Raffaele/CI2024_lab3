# N-Puzzle Solver

This project provides an implementation for solving the **N-Puzzle Problem**, a classic combinatorial puzzle involving a sliding block mechanism. The solution utilizes heuristic search algorithms to find optimal or near-optimal paths efficiently.

## Algorithms
- **A***: A* search is one of the most widely used informed search algorithms, combining the path cost from the start node g(n) with the heuristic estimate h(n) to create a total cost function `f(n)=g(n)+h(n)`.
- **SMA*** (Simplified Memory-Bounded A*): SMA* is designed to fully utilize available memory while optimizing search efficiency. When memory is full, SMA* discards the worst leaf (highest f-value) and backs up its f-value to the parent node. This enables SMA* to "remember" paths without excessive memory use.



## Features

- `h(n)`: The sum of the Manhattan distances (horizontal and vertical distances) of the tiles from their goal positions.
- `memory_limit = n`, the SMA* algorithm is allowed to store up to n potential states (nodes) at a time during the search process. If the number of states exceeds this limit, it discards the least promising state (based on the highest estimated total cost, or f-cost) to stay within the memory constraints. This ensures the algorithm operates efficiently within the specified resource bounds.

| Puzzle Size | Initial State            | Goal State               | Steps to Solve | Evaluated Actions |Efficiency| Algorithm  |
|:-------------:|:---------------------------:|:--------------------------:|:----------------:|:---------------------:|:-------:|:-----:|
| 8-Puzzle    | `[[2, 3, 5], [6, 7, 1], [0, 4, 8]]` | `[[1, 2, 3], [4, 5, 6], [7, 8, 0]]` | 20           | 338   |  0.0592   | A* Search |
| 8-Puzzle    | `[[2, 3, 5], [6, 7, 1], [0, 4, 8]]` | `[[1, 2, 3], [4, 5, 6], [7, 8, 0]]` | 36         | 302    | 0.1192 | SMA |
