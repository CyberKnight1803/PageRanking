# Assignment-2: Page Ranking of Web Graphs


## 2A

The first two steps remain same for the both the parts

1. Construct Adjacency Matrix using `constructAdjM(input_file)`
2. Construct Probability transition Matrix `constructProbTransMatrix(V, adjM, random_teleport=True, alpha=0.9)` where alpha is the teleport operation probability
   
For part-1:
3. Compute principle left eigenvector via `compute_principle_left_eigen_vector(P)` which will be treated as steady state probabilities as well as ranks 

For part-2:
3. Use power iteration method until the vector converges. `power_iteration`. The converged vector is treated as steady-state vector.

4. To get the Pages in ranked order, use `get_ranks(pi)` where you feed in the steady state probabilities.

## 2B