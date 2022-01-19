# 8-Queens-by-Simulated-Annealing

![SimulatedAnnealing](https://github.com/smitanannaware/8-Queens-by-Simulated-Annealing/blob/main/SimulatedAnnealing/animation.gif)


Simulated annealing term borrowed from metallurgy. Annealing is the process of heating a metal and letting it cool down slowly to lock in the stable locations of the molecules. In Simulated Annealing algorithm combines random walk where random successor is chosen uniformly from the set of successors and the hill climbing algorithm. Combining random walk with hill climbing yields efficiency and completeness.

Simulated annealing always moves uphill if possible, like hill climb. But it allows some bad moves as opposed to hill climb when the temperature is high. As temperature decreases it reduces the chances of selecting bad moves. Optimality is guaranteed with slow annealing schedule. In this project we will be analyzing the effect of annealing schedule on completeness of the algorithm for solving 8-queens problem.

# N-Queens problem
The N-queens problem is about placing ‘n’ queens on an ‘n × n’ chessboard. Each queen occupies one square on the board and no two queens share the same square.
Two queens would attack each other if either of them can travel diagonally, horizontally, vertically, or and hit the square the other queen is on. The problem is to place the queens such that no two queens are attacking each other. Goal state is achieved when all the n queens are place such that no two queens are attacking each other in any way possible. The N-queens problem can be solved using Simulated Annealing algorithm.

#	Implementation

Following the pseudocode, implementation of simulated annealing is done using Python programming language. 
As the probability of selection of “bad” state is evaluated by below function

Probability = e<sup>∆E/T</sup>

where T is temperature varies based on cooling schedule, 

∆E = Error function i.e., Heuristic value of current state - Heuristic value of next state,

Below are the parameters affecting the probability function is discussed.

##	Parameters used

•	Starting temperature = 1500000000
Starting temperature is set to sufficiently high to allow virtually all transitions to be accepted at the beginning of the algorithm regardless of whether they increase the error function or not.
  
•	Temperature bound = 1e-200
In contrast to the starting temperature, the stopping temperature kept sufficiently low for an extended period for the algorithm to reach towards the global maximum in this case.

•	Cooling schedule = 0 to 1
The cooling schedule is biggest factor affecting the algorithm’s ability to reach an optimal solution. Here geometric cooling technique is used whose value range from 0 to 1. Higher the number slower the temperature rate and vice versa. This is dynamically taken as input from user before running the algorithm.

