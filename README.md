# GeneticAlgorithm
A genetic algorithm (GA) is a search heuristic inspired by the principles of natural selection and genetics. It is used to find approximate solutions to optimization and search problems. Here’s a brief overview of how a genetic algorithm works:

1. **Initialization**: Start with a randomly generated population of candidate solutions, represented as chromosomes (strings of genes).

2. **Selection**: Evaluate the fitness of each individual in the population. Fitness is a measure of how good a solution is with respect to the problem being solved. Select individuals based on their fitness, favoring those with higher fitness to pass their genes to the next generation.

3. **Crossover (Recombination)**: Combine pairs of selected individuals (parents) to create offspring. This is done by swapping segments of their chromosomes to produce new chromosomes (children), inheriting features from both parents.

4. **Mutation**: Introduce small random changes to individual chromosomes to maintain genetic diversity within the population. This helps the algorithm to explore new potential solutions and avoid local optima.

5. **Replacement**: Form a new generation by replacing some or all of the old population with the new offspring. The process then repeats from the selection step.

6. **Termination**: The algorithm stops when a termination condition is met, which could be a solution that satisfies a predefined fitness level, a maximum number of generations, or a convergence of the population.

Through these steps, the genetic algorithm evolves the population towards better solutions over successive generations.

**Example** :

Q1. You have 5 particles. Now randomly select 3 coordinates for each of them. Calculate LJ potential. Write a program by using genetic algorithm to find the minimum potential. Find the optimal coordinates. (Given : epsilon = 1, sigma = 1, coordinates should be between 0.5 to 3)
Q2. You have a function. for example, here function is X^2*exp(-x^2). You have to find maxima of that function.

