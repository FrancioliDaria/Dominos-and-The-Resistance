Artificial Intelligence - Project 2: Dominos and The Resistance
Overview
This project implements two distinct AI problems:

Domino Problem: A solver for different levels of the classic domino game, where the goal is to arrange dominoes in specific ways.
The Resistance Puzzle: An AI solution to deduce the roles of players in the game "The Resistance", including identifying spies, traitors, and members of the resistance.
The project leverages AI techniques such as constraint satisfaction and logical inference to solve both puzzles.

Contents
Domino Problem
Seven Squares (Problem 1): Arrange seven dominoes to satisfy constraints based on matching numbers on adjacent squares.
Seven Squares (Problem 2): Arrange the dominoes such that the sums of the numbers on adjacent squares are equal.
The Resistance Puzzle
A logical deduction system that infers the roles of players (spies, traitors, and resistance members) based on their interactions and certain assumptions.
Table of Contents
Installation
How to Use
Domino Problem
Seven Squares Problem 1
Seven Squares Problem 2
The Resistance Puzzle
Technologies Used
License
Installation
To run this project, you'll need a working Prolog environment as the logic is implemented in Prolog.

Install SWI-Prolog:

Go to SWI-Prolog Downloads and follow the instructions for your operating system.
Clone the repository:
git clone <repository_url>

Run the project:

Navigate to the project directory and open the Prolog files to run the code:
swipl <your_prolog_file>.pl

How to Use
Domino Problem
Seven Squares (Problem 1)
In this problem, the task is to arrange seven squares with dominoes so that adjacent dominoes match on their ends. The code will attempt to find all valid solutions to this arrangement.

Load the Prolog file related to this problem.
Run the solver, and the system will attempt to find a valid configuration.
Results will be shown as different valid configurations of the dominoes.
Seven Squares (Problem 2)
This problem involves arranging the dominoes in a way that the sum of the numbers on adjacent dominoes equals the same value across all four sides of the arrangement.

Load the Prolog file related to this problem.
Run the solver.
The system will attempt to find configurations where the sum of numbers on the edges is equal.
The Resistance Puzzle
In this puzzle, you must deduce the roles of the players (Resistance members, Spies, Traitors, etc.) from a series of logical assumptions and interactions.

Open the Prolog file that contains the rules and assumptions.
The system will evaluate the logical relationships and provide conclusions based on the set conditions.
Results will tell you which players belong to the Resistance, which are Spies, and which are Traitors.
Domino Problem
Seven Squares Problem 1
This problem involves arranging the pieces in such a way that adjacent dominoes have matching numbers. Here's the Prolog code used to solve this:

assign(domain_size, 7).
assign(max_models, -1).
set(arithmetic).
formulas(assumption).
c1 = c8 & c2 = c3 & c4 = c5 & c6 = c7.
end_of_list.
formulas(goal).
-((c1 = c3 | c1 = c4) & (c2 = c3 | c2 = c4)).
...
Seven Squares Problem 2

This problem involves arranging the dominoes such that the sums on each side of the arrangement are equal. Here's the Prolog code used to solve this:

assign(domain_size, 7).
assign(max_models, -1).
set(arithmetic).
formulas(assumption).
c1 + c2 + c3 = c3 + c4 + c5 & c3 + c4 + c5 = c5 + c6 + c7 & c5 + c6 + c7 = c7 + c8 + c1.
end_of_list.
formulas(goal).
-(c1 = c3 | c1 = c4 | c2 = c3 | c2 = c4).
...
The Resistance Puzzle
This portion of the project aims to solve the puzzle of determining who the Resistance members, Spies, and Traitors are based on interactions and assumptions.

Prolog Code

Here’s an example of how we define the roles and interactions:

% constants: a, b, c, d, e, f (the players)
% predicate Resistance(x): x is a resistance
% predicate Spy(x): x is a spy
% predicate Traitor(x): x is a traitor
% predicate Government(x): x is a government
...

formulas(assumptions).
spy(a).
resistance(b).
resistance(c).
traitor(d).
goverment(e).
goverment(f).
...
Example Interaction
The system will deduce that certain players know each other or have attacked one another, helping us figure out the roles of each player.

Technologies Used
Prolog: A logic programming language used for solving AI problems like the ones presented in this project.
SWI-Prolog: The environment used to run the Prolog code.
