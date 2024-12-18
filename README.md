# Travelling Thief Problem Optimizer

This project implements a solution for the **Travelling Thief Problem (TTP)**, which combines aspects of the **Travelling Salesman Problem (TSP)** and the **Knapsack Problem (KSP)**. The project uses algorithms to optimize the path and item selection simultaneously for maximum efficiency.

---

## What is the Travelling Thief Problem (TTP)?

The **Travelling Thief Problem** is a combinatorial optimization problem that combines two classical problems:

- **Travelling Salesman Problem (TSP):**  
  Find the shortest route to visit a set of cities exactly once and return to the starting point.

- **Knapsack Problem (KSP):**  
  Maximize the value of items selected to fit within a weight-constrained knapsack.

The TTP introduces a unique challenge: as the thief travels, the weight of the items collected affects the travel speed. This creates a trade-off between collecting valuable items and minimizing the travel cost.

---

## Why is TTP Important?

The TTP models real-world scenarios where multiple objectives must be optimized simultaneously, such as:

- **Logistics and Supply Chain Optimization:**  
  Efficiently plan routes and item pickups for delivery operations.

- **Path Planning for Drones or Vehicles Carrying Cargo:**  
  Optimize routes for drones or autonomous vehicles while considering payload constraints.

- **Resource-Constrained Scheduling Problems:**  
  Balance resource usage and task efficiency under limiting factors.

It serves as a benchmark problem for testing and developing optimization algorithms that can handle multiple interdependent constraints.

---

## Project Structure

The project has the following folder structure:

NIC_CA2_group_project-main/
│
├── resources/                     # Dataset files and configuration
│   ├── a280-n279.txt              # Dataset index 0
│   ├── a280-n1395.txt             # Dataset index 1
│   ├── a280-n2790.txt             # Dataset index 2
│   ├── fnl4461-n4460.txt          # Dataset index 3
│   ├── fnl4461-n22300.txt         # Dataset index 4
│   ├── fnl4461-n44600.txt         # Dataset index 5
│   ├── pla33810-n33809.txt        # Dataset index 6
│   ├── pla33810-n169045.txt       # Dataset index 7
│   ├── pla33810-n338090.txt       # Dataset index 8
│   └── param_properties           # Parameter configuration file
│
├── src/                           # Source code files
│   ├── solver.py                  # Main program entry point
│   ├── tsp_algo.py                # TSP algorithms implementation
│   ├── nsga_util.py               # Utility for NSGA-based optimization
│   ├── pack_util.py               # Knapsack packing logic
│   ├── plotter.py                 # Visualization of results
│   ├── file_util.py               # File I/O utilities
│   ├── three_opt.py               # 3-opt algorithm for TSP improvement
│   ├── Route.py, Node.py, etc.    # Supporting classes for route and graph
│   ├── Dataset.py                 # Dataset management and parsing
│   ├── path_util.py               # Path management utilities
│   └── Params.py                  # Reads and applies parameters
│
└── README.md                      # Project documentation

## How to Run the Project

### Parameter Configuration

#### 1. To configure the parameters for the project, update the file located at `resources/param_properties`. Below is a list of the key parameters and their descriptions:

| **Parameter**         | **Type**    | **Description**                                                         |
|------------------------|------------|-------------------------------------------------------------------------|
| `population_size_nsg` | `int`      | Population size for the NSGA algorithm.                                 |
| `evaluations_tsp`      | `int`      | Rounds of fitness evaluation in the TSP.                                |
| `run_local_tsp`        | `bool`     | Optimize each node in the TSP (`True`/`False`).                         |
| `tournament_size_ksp`  | `int`      | Tournament size for fitness testing in the KSP.                         |
| `num_generations_ksp`  | `int`      | Rounds of fitness evaluation in the KSP.                                |
| `fill_rate_ksp`        | `float`    | Knapsack fill rate as a percentage.                                     |
| `dataset_idx`          | `int`      | Index of the dataset to load (`0–8`).                                   |

#### 2. Run the Solver:
Execute the solver.py file in the src folder:
```bash
python src/solver.py
```

#### 3. Output:
The program will:

Optimize the TSP and KSP solutions.
Display the results, including the selected path and items.
Save the outputs or visualizations in the appropriate directories (configurable).

## Dataset Information

The datasets for the **Travelling Thief Problem** are stored in the `resources/` folder. Below is the mapping of dataset indexes (`dataset_idx`):

| **Index** | **Dataset Name**            | **Size**  |
|-----------|-----------------------------|-----------|
| 0         | `a280-n279.txt`             | 9 KB      |
| 1         | `a280-n1395.txt`            | 28 KB     |
| 2         | `a280-n2790.txt`            | 50 KB     |
| 3         | `fnl4461-n4460.txt`         | 153 KB    |
| 4         | `fnl4461-n22300.txt`        | 508 KB    |
| 5         | `fnl4461-n44600.txt`        | 910 KB    |
| 6         | `pla33810-n33809.txt`       | 1.3 MB    |
| 7         | `pla33810-n169045.txt`      | 4.3 MB    |
| 8         | `pla33810-n338090.txt`      | 7.6 MB    |

---

## Key Files

- **`solver.py`**: The main script to execute the solution.  
- **`tsp_algo.py`**: Contains the TSP algorithms (e.g., 3-opt).  
- **`pack_util.py`**: Manages the Knapsack problem logic.  
- **`nsga_util.py`**: Implements the optimization using NSGA algorithms.  
- **`plotter.py`**: Generates plots/visualizations for results.  


## Visualizations

The project supports visualizing:

- **TSP Path**: Optimized travelling path between nodes.  
- **Knapsack Selection**: Selected items for the knapsack.  

---

## References

- **Original Problem**: [https://github.com/blankjul/gecco19-thief/tree/master](https://github.com/blankjul/gecco19-thief/tree/master)

---
