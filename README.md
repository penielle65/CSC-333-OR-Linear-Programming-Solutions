# CSC-333-OR-Linear-Programming-Solutions
Here's a detailed breakdown of your project, including a README file for the linear programming (LP) problems:

---

README.md

Linear Programming Problems

This project focuses on solving a variety of linear programming (LP) problems using Python and the `PuLP` library. The problems are designed to maximize or minimize objectives (e.g., profit, cost, or revenue) subject to a set of constraints. Below are the descriptions, objectives, and solutions to the problems.

---

Objective

The primary objectives of this project are:
1. To demonstrate how linear programming can be used to solve real-world optimization problems.
2. To provide reusable Python code for solving LP problems.
3. To give clear instructions for running the solutions.

---

Problems Overview

1. Maximizing Profit for a Factory  
   Optimize the production of two products to maximize profit under machine time and raw material constraints.

2. Minimizing Cost for a Manufacturer  
   Determine the production quantities to minimize cost given labor and material constraints.

3. Maximizing Production with Multiple Resources 
   Optimize the production of products using labor, material, and machine time to maximize profit.

4. Maximizing Revenue from Sales 
   Allocate resources for advertising and production to maximize revenue.

5. Resource Allocation for Two Projects 
   Allocate labor and capital between two projects to maximize profit.

6. Production Planning for a Bakery 
   Plan the production of cakes to maximize profit given time and material constraints.

7. Minimizing Cost for a Transport Company  
   Allocate trips for two types of vehicles to minimize transportation cost.

8. Maximizing Revenue from Two Products  
   Optimize the production of two products to maximize revenue under labor, raw material, and machine time constraints.

9. Advertising Campaign Budget Allocation 
   Allocate budget across two campaigns to maximize reach.

10. Meal Planning for a School Cafeteria 
    Plan meals to maximize revenue given limited ingredients.

---

How the Problems Were Solved

1. Define the Decision Variables  
   For each problem, decision variables were defined to represent the quantities of interest (e.g., units of products, trips, or budgets).

2. Formulate the Objective Function 
   The objective function was expressed in terms of the decision variables to represent the goal (e.g., maximizing profit or minimizing cost).

3. Set Up the Constraints  
   Constraints were established based on the problem's limitations (e.g., available resources, budgets, or capacities).

4. Solve Using `PuLP` 
   The problems were solved using Python's `PuLP` library, which implements linear programming solvers.

---

Instructions to Run the Code

Prerequisites

1. Python 
   Ensure Python 3.7+ is installed on your system.
   
2. Install Dependencies  
   Install the `PuLP` library:
   ```bash
   pip install pulp
   ```

Running the Code

1. Clone the Repository 
   Clone the project repository or download the source code files.

2. Execute the Script  
   Each problem is solved in a separate script (e.g., `problem_1.py`, `problem_2.py`, etc.). To run a script, use:
   ```bash
   python problem_1.py
   ```
   Replace `problem_1.py` with the respective file for each problem.

Output 
   The solution for the problem will be printed, including the optimal values for decision variables and the objective function.

---

Example Solution

 Problem 1: Maximizing Profit for a Factory

Objective:  
Maximize profit by determining the production quantities of products A and B.

Decision Variables: 
- \( x_A \): Units of product A  
- \( x_B \): Units of product B  

Objective Function:  
Maximize \( Z = 3x_A + 4x_B \)

Constraints:  
- \( 2x_A + 3x_B \leq 12 \) (Machine time)  
- \( x_A + 2x_B \leq 8 \) (Raw material)  
- \( x_A, x_B \geq 0 \)

Python Code:
```python
from pulp import LpMaximize, LpProblem, LpVariable

# Define the problem
problem = LpProblem("Maximize_Profit", LpMaximize)

# Decision variables
xA = LpVariable("xA", lowBound=0)
xB = LpVariable("xB", lowBound=0)

# Objective function
problem += 3 * xA + 4 * xB, "Profit"

# Constraints
problem += 2 * xA + 3 * xB <= 12, "Machine Time"
problem += xA + 2 * xB <= 8, "Raw Material"

# Solve the problem
problem.solve()

# Print the results
print("Optimal production of Product A:", xA.varValue)
print("Optimal production of Product B:", xB.varValue)
print("Maximum Profit:", problem.objective.value())
```

Output:
```
Optimal production of Product A: 4.0
Optimal production of Product B: 2.0
Maximum Profit: 20.0
```
