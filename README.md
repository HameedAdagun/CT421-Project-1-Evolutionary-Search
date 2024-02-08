# Part A - Initial search landscape

## Description of code struture and representation
Initialize populuation
This is the same for all three parts of the assignment. This function generate pop_size(500) strings.
These strings are 30 bits long. Each solution is represented as a 30 long bit string.

Calculate fitness
1.1
This function iterates through the population and sums all the one's. For example, if they were 30
one's in a bit string, this function would return 30.

1.2
In this part the function calculates the fitness based on how many of the bit match with the target
string.

1.3
This is similar is 1.1 however the is a deceptive fitness. Where the bit string has all zero the 
fitness would be 2 x the length of the string.

Mutate
Based on the mutation rate, this function gets a random bit in the bit strings and flips it.

Crossover
For this function you need two parents. It gets a random point in the bit string. The function
then creates two children, child1 and child2, by combining portions of the parents.
For child1, it takes the portion of parent1 up to the crossover point and combines it with the portion
of parent2 after the crossover point. For child2, it takes the portion of parent2 up to the crossover
point and combines it with the portion of parent1 after the crossover point.

Main genetic algorithm loop
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
In both 1.1 and 1.2 the gentic algorithm hits the optimal fitness of 30. Howvwer in 1.3 this is not the case. This 
is because the landscape is deceptive. The optimal fitness in 1.3 is 2 x the length of the string which would be 60.
The landscape leads the GA to believe that all one's is the solution but actually it is all zero's.

# Part B - Bin-packing problem

## Description of code struture and representation


## Description of fitness function


## Insights into the problem landscape


 
