# INFO6205_514
README

Problem Statement:
The heat transfer Q for a spherical reactor of diameter D is given by the equation:
Q = hTA ---- 1
where
h -> heat transfer co-efficient
T -> temperature difference from the ambient 
A-> surface area of sphere given by πD 2
To find the diameter for the minimum heat transfer for a spherical reactor using genetic algorithms.

Pre – run steps:
1.	Convert to a single variable equation 
There is a constraint:
The strength equation is DT = 20 
This is due to the material limitations
Applying this in 1:
Q = 62.83(2D + 0.91D -0.2)
The first term increases with D and the second decreases with D 
We need to find optimum value of D for achieve minimum Q
2.	Select decimal accuracy for D 

We selected one decimal accuracy for D. 64 bits are required to represent 6.3 
111111 represents 63 so 63/10 would be 6.3
So, we take D values < 6 in our experiment

3.	Formulate fitness function
We tested for various combinations of D, the value does not exceed 850.So we can be sure Y does not become negative
So, we selected the fitness function as below to convert the problem to a maximizing problem instead of minimization
Y = 850 - Q 


Packages:
We have three packages:
1.	Model
2.	Main
3.	Functions

1.	Model has the following:
Order: reactor , fitness value and Heat Coefficient
Genotype : reactor list, Heat Coefficient list , phenotype and representation for Genotype
Phenotype : Order and average heat released
Population : List of Genotype
Reactor : made of diameter

2.	Main
MainDriver class: 
Main method: creates a population, genotype and reactor list. Reactor list is added to the genotype. Order is then calculated for the genotype 
A loop is created for creating generations. In each generation, crossover is applied on the genotype and subsequently mutation is done too for optimum results. Collection sort is used to sort a map which has fitness value as key and diameter as values. The loop breaks when optimum results are achieved.ie. the fitness value is over 0.7 and the heat transfer is above 746.
Create and show GUI method: To generate graph

3.	Functions : FitnessFunction Class
We have the following methods :
heatCoeffQ – to find Q
fitnessValue – calculate relative fitness 
doubleToBin – convert double values of diameter to binary
getChild – selects mother and father for crossover which was called in main to get new generation. The string r is already sorted on fitness value and the 0,2 and 1,3 positions are selected for cross over
characterInterchange – The child is created with first 3 binary digits of father and the other three of mother and vice versa for next child
calculateDiameter – Based on the fitness, we take the highest fitness diameter twice and the second and third is taken once for the next generation


 Unit Test cases 

1.Calculation of heat co-efficient values
2.Calculation of total co-efficient of a generation
3.Fitness value calculations
4.Double to binary conversions

 
Conclusion: 

The optimum solution for heat transfer is found to be 103 watts for diameter 0.65 using calculus.

We observe that the genetic algorithm applied to this problem performs really well and gives us the optimum D value as 104 Watts (850-746), very close to solution obtained by calculus.


 











