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

import numpy as np
import random

mv = []

F = []
function = []
pi = []
fitness = []
for i in range(10):
        F.append(np.random.uniform(1, 10, size=10))
        func_values = []
        for j in F[i]:
            f = j ** 2 * np.exp(-j ** 2)
            func_values.append(f)
        function.append(sum(func_values))
print(f"parent population :\n {F}")
#print(f"function :{function}")

for i in function:
        fitness.append(np.exp(i))
#print(f"fitness :{fitness}")

for i in fitness:
        pi.append(i / sum(fitness))
#print(f"probability: {pi}")
pi1 = np.sort(pi)
print(f"sorted pi: {pi1}")

**Parent pool formation**
You will get a range.Then you have to normalise it.
Generate a random value between 0 to 1.
if it falls between 0 - sort_pi[0], then pick the first chromosome
if falls between sort_pi[0] - sort_pi[1], pick second chromosome
. . . . . . .
. . . . . . .

x = np.random.rand(10)
#print(x)

parent_pool = []
for i in x:

    # Find the index in sort_pi that corresponds to i in sort_pi
    idx = np.searchsorted(pi1, i)
    #print(idx)
    # Adjust idx to stay within the bounds of sorted_norm
    idx = min(idx, len(pi1) - 1)
    #print(idx)
    # Use idx to find the index in norm_fit and fun
    selected_idx = np.where(pi == pi1[idx])[0][0]
    #print(selected_idx)
    # Append the value from fun at the selected index to parent_pool
    parent_pool.append(F[selected_idx])

print(parent_pool)

**Cross over**
now you have to generate father and mother population. and randomly change some segments between these 2 to cross over. After crossing over, join them again and it will be child population.

def perform_crossover(parent_pool):
    father = random.sample(parent_pool, 5)
    mother = random.sample(parent_pool, 5)
    offspring = []

    for j in range(5):
        a = np.random.randint(1, len(father[j]))

        f = father[j].copy()  # Make a copy to avoid mutating the original parent
        m = mother[j].copy()

        father_offspring = np.concatenate((f[:a], m[a:]))
        mother_offspring = np.concatenate((m[:a], f[a:]))

        offspring.append(father_offspring)
        offspring.append(mother_offspring)

    return offspring
new_population = perform_crossover(parent_pool)
print(new_population)

**Mutation**
Now from child population, randomly select a gene and replace it with random number.

l1 = random.randint(0, 9)
l2 = random.randint(0, 9)
k1 = new_population[l2][l1]

print(l2,l1)
m1 = random.uniform(1, 11)
new_population[l2][l1] = m1

print(new_population)

After completing mutation step, calculate the fitness, you will see that fitness will be greater than the initial one. By iterating these steps, you will find maxima of the function.
