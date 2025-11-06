# Genetic Algorithm for TSP using Inver Over and Inversion Mutation

This project implements a **Genetic Algorithm (GA)** to solve the **Travelling Salesman Problem (TSP)**.  
The algorithm combines two evolutionary operators:
- **Inver Over** 
- **Inversion Mutation**

The algorithm also uses **Tournament Selection** to choose parents and a **Mutation Rate** to decide whether to apply Inver Over or Inversion Mutation.

---

## ⚙️ Algorithm Description

### 1. Initialization
A population of random tours (permutations of cities) is generated using:
```python
def generate_population(pop_size, n):
    population = [random.sample(range(n), n) for _ in range(pop_size)]
    return population
```
### 2. Generations Loop
There are N iterations. Firstly we apply tournament selection to choose the best parent to generate our offspring, so we decide, using a mutation_rate whether to apply Inver Over or Inversion Mutation.
```python
if random.random() < MUTATION_RATE:
            child = inversion_mutation(parent)
        else:
            child = inver_over(parent, population)

        offspring.append(child)
```

## Example output

Initial best fitness: 3737.89\
Gen   0 | Best dist: 2147.96\
Gen  10 | Best dist: 1497.66\
Gen  20 | Best dist: 1497.66\
...\
Gen 190 | Best dist: 1497.66
