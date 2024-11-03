# Travelling Salesman Problem

Explore optimization techniques for solving the **TSP** problem with Greedy Approach. After finding the best Greedy solution, use this solution as starting point for the Evolutionary Algorithm.

## Description
*Greedy approach* moves to the nearest city.
*Evolutionary algorithm* based on *mutation* and *cross-over* operators. 
The performance of the algorithms are evaluated in terms of travelling distance and the number of steps needed.
TSP instances are provided in the following Wolfram Notebook: https://www.wolframcloud.com/obj/giovanni.squillero/Published/Lab2-tsp.nb.

## Greedy Algorithm
The nearest neighbour (NN) algorithm (a greedy algorithm) lets the salesman choose the nearest unvisited city as his next move. This algorithm quickly yields an effectively short route. For N cities randomly distributed on a plane, the algorithm on average yields a path 25% longer than the shortest possible path; however, there exist many specially-arranged city distributions which make the NN algorithm give the worst route. This is true for both asymmetric and symmetric TSPs Rosenkrantz et al. showed that the NN algorithm has the approximation factor Θ(log|V|) for instances satisfying the triangle inequality.

The *Approx. Algorithms* results were obtained through the use of the NetworkX library, which includes a selection of approximation algorithms for the TSP problem.
The function *travelling_salesman_problem* allows for incomplete graphs by finding all-pairs shortest paths, effectively converting the problem to a complete graph problem. It calls one of the approximate methods on that problem and then converts the result back to the original graph using the previously found shortest paths.

* All costs are measured in Km *

| Instance | N. cities  | Greedy Route Cost | Approx. Algorithms |        My EA       |
| -------- | ---------- | ----------------- | ------------------ | ------------------ |
| Vanuatu  |     8      |       1475.53     | 1345.54(Annealing) |       1345.54      |
| Italy    |    46      |       4436.04     | 4436.04(Annealing) |       4310.57      |
| Russia   |   167      |      40051.58     | 37223.93(Christof.)|      38640.09      |
| US       |   340      |      46244.35     | 42307.30(Christof.)|      45617.90      |
| China    |   746      |      61660.71     | 54456.76(Christof.)|      59427.00      |

## Evolutionary Algorithm
In computational intelligence (CI), an *evolutionary algorithm* (EA) is a subset of evolutionary computation, a generic population-based metaheuristic optimization algorithm. Evolutionary algorithms often perform well approximating solutions to all types of problems because they ideally do not make any assumption about the underlying fitness landscape.

**Process**
Step One: Generate the initial population of individuals starting from the best Greedy solution.

Step Two: Repeat the following regenerational steps until termination (time limit, sufficient fitness achieved, etc.):
  - Evaluate the fitness of each individual in the population
  - Select the individuals for reproduction based on their fitness. (Parents)
  - Breed new individuals through crossover and mutation operations to give birth to offspring.
  - Replace the least-fit individuals of the population with new individuals.
