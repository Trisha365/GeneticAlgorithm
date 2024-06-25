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

**Initialisation**
You have a function. for example, here function is X^2*exp(-x^2). You have to finc maxima of that function.
For this, we use an algoritm that is similar to processes occuring into chromosome such as crossing over, mutation etc.
1. In the first step, you have to generate 10 chromosome with random genes (10x10 matrix, row represents chromosome and column represents genes.).
2. Calulate the function. then you will get a list with 10 elements.
3. Calulate fitness function.(to find maxima, use exp(f(x)), to find minima use exp(-f(x)))
4. Then calculate probability of each fitnessand sort it.

**Parent pool formation**
You will get a range.Then you have to normalise it.
Generate a random value between 0 to 1.

if it falls between 0 - sort_pi[0], then pick the first chromosome

if falls between sort_pi[0] - sort_pi[1], pick second chromosome

. . . . . . .
. . . . . . .

**Cross over**

now you have to generate father and mother population. and randomly change some segments between these 2 to cross over. After crossing over, join them again and it will be child population.

**Mutation**

Now from child population, randomly select a gene and replace it with random number.

After completing mutation step, calculate the fitness, you will see that fitness will be greater than the initial one. By iterating these steps, you will find maxima of the function.
