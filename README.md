# Part A - Initial search landscape

## Description of code struture and representation
Initialize populuation
This is the same for all three parts of the assignment. This function generate pop_size(500) strings.
These strings are 30 bits long. Each solution is represented as a 30 long bit string.

### Calculate fitness
**1.1** <br>
This function iterates through the population and sums all the one's. For example, if they were 30
one's in a bit string, this function would return 30.

**1.2** <br>
In this part the function calculates the fitness based on how many of the bit match with the target
string.

**1.3** <br>
This is similar is 1.1 however the is a deceptive fitness. Where the bit string has all zero the 
fitness would be 2 x the length of the string.

### Mutate
Based on the mutation rate, this function gets a random bit in the bit strings and flips it.

### Crossover
For this function you need two parents. It gets a random point in the bit string. The function
then creates two children, child1 and child2, by combining portions of the parents.
For child1, it takes the portion of parent1 up to the crossover point and combines it with the portion
of parent2 after the crossover point. For child2, it takes the portion of parent2 up to the crossover
point and combines it with the portion of parent1 after the crossover point.

### Main genetic algorithm loop
The loop starts by initializing the population and an empty list to store the history of average fitness values.
It then iterates indefinitely, calculating the fitness of each individual in the population and computing the
average fitness. If the average fitness surpasses the predefined threshold, the loop terminates. Otherwise,
it selects parents based on fitness, performs crossover and mutation operations to create offspring, and updates
the population accordingly. This process continues until the termination condition is met.


## Plots of the performance of the genetic algorithm
![image](https://github.com/HameedAdagun/CT421-Project-1-Evolutionary-Search/assets/144913969/eed4c293-40f0-420d-a3cd-187023b59a69)
![image](https://github.com/HameedAdagun/CT421-Project-1-Evolutionary-Search/assets/144913969/56ebb97f-7e82-4a94-be7d-63804d4039a6)
![image](https://github.com/HameedAdagun/CT421-Project-1-Evolutionary-Search/assets/144913969/12dcdbc2-2740-4384-9503-9d1b6bffebfd)


## Description of your results
In both 1.1 and 1.2 the genetic algorithm (GA) hits the optimal fitness of 30. Howvwer in 1.3 this is not the case. This 
is because the landscape is deceptive. The optimal fitness in 1.3 is 2 x the length of the string which would be 60.
The landscape leads the GA to believe that all one's is the solution but actually it is all zero's.

# Part B - Bin-packing problem

## Description of code struture and representation
### Pick random integers and pick integers
pick_random_integer: This function randomly selects an integer based on weights provided in a dictionary (item_weights). 
It returns the selected integer.
pick_integers: This function picks integers using the pick_random_integer() function and organizes them into sublists. 
It ensures that each sublist contains at most 46 integers. It iterates through the integers, assigning them to sublists
based on their index modulo 46. It also decreases the count of each chosen integer in the item_weights dictionary and
removes it if its count becomes 0. Finally, it appends any remaining integers to the sublists in sequence. The function
returns a list of sublists containing the selected integers. The sublists acts like bins.

### Mutate
This is very similar to the mutation function in part 1 except the mutatation rate is called on each bit.

### Crossover
Again very similar to part 1. In this function the crossover rate is included.

### Main genetic algorithm loop
This main genetic algorithm loop iterates over a predefined number of generations. In each iteration:
- Fitness values are calculated for the chosen sublists (presumably representing individuals in the population). Also the number of bins is printed.
- The fitness values are then converted into probabilities.
- Parents are selected based on their fitness probabilities using a roulette wheel selection method.
- Children are created through crossover and mutation operations.
- The population (chosen_sublists) is updated with the new generation, where the children replace the least fit individuals.

## Description of fitness function
The calculate_fitness function takes a population of subsets as input. It computes the fitness of each individual (subset) in
the population by summing up the elements of each subset. You can think of this like adding the items in a bin. If the sum exceeds
a predefined capacity (bin_capacity), the fitnessis set to 0. The function then returns a list containing the fitness values for each
individual in the population. 

## Insights into the problem landscape


 
