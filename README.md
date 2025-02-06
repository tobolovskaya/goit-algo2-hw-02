# task_1 3D Printer Queue Optimization

## Overview
This project focuses on optimizing the **3D printing queue** in a university laboratory, ensuring efficient scheduling of print jobs based on **priority and printer constraints**.

## Problem Statement
The goal is to optimize the order of **print jobs** by considering:
- **Priority levels**:
  - **1 (Highest)**: Course/diploma projects
  - **2**: Laboratory assignments
  - **3 (Lowest)**: Personal projects
- **Printer constraints**:
  - Maximum print volume
  - Maximum number of models per batch

## Implementation Details
### **Algorithm (`optimize_printing`)**
- Sorts tasks by **priority** (higher first) and **print time**.
- Groups models within the allowed **volume and count constraints**.
- Calculates total **printing time** as the maximum print time of each batch.
- Returns:
  - **print_order**: The optimal order of print jobs.
  - **total_time**: The overall print time required.

## Expected Input & Output
### **Input:**
```python
print_jobs = [
    {"id": "M1", "volume": 100, "priority": 1, "print_time": 120},
    {"id": "M2", "volume": 150, "priority": 1, "print_time": 90},
    {"id": "M3", "volume": 120, "priority": 1, "print_time": 150}
]
constraints = {"max_volume": 300, "max_items": 2}
```

### **Output:**
```json
{
    "print_order": ["M1", "M2", "M3"],
    "total_time": 270
}
```

## Running the Code
Execute the script using:
```sh
python script.py
```

The script runs test cases for:
1. **Same priority jobs**
2. **Different priority jobs**
3. **Jobs exceeding printer constraints**

## Conclusion
This project implements an **efficient greedy algorithm** to schedule 3D print jobs while respecting hardware limitations and prioritizing important tasks.



# task_2 Rod Cutting Optimization

## Overview
This project implements an optimization algorithm for the **Rod Cutting Problem**, which determines the best way to cut a rod to maximize profit. The solution includes two dynamic programming approaches:

1. **Memoization (Top-Down Approach)**: Recursively computes the optimal cuts while storing intermediate results to avoid redundant calculations.
2. **Tabulation (Bottom-Up Approach)**: Iteratively builds up the solution using a table to store the maximum profit for each rod length.

## Problem Statement
Given:
- A rod of length **N**.
- A list of prices where `prices[i]` represents the price of a rod of length `i + 1`.

Find the optimal way to cut the rod (or not cut at all) to achieve the highest possible profit.

## Implementation Details
### **1. Memoization Approach (`rod_cutting_memo`)**
- Uses recursion to explore different ways of cutting the rod.
- Stores results in a dictionary to prevent recomputation.
- Returns a dictionary containing:
  - **max_profit**: The highest obtainable profit.
  - **cuts**: The optimal set of rod lengths.
  - **number_of_cuts**: The total number of cuts performed.

### **2. Tabulation Approach (`rod_cutting_table`)**
- Uses an iterative **bottom-up** method.
- Builds a table to store optimal solutions for subproblems.
- Returns the same dictionary format as the memoization approach.

## Expected Input & Output
### **Input:**
```python
length = 5
prices = [2, 5, 7, 8, 10]
```

### **Output:**
```json
{
    "max_profit": 12,
    "cuts": [2, 2, 1],
    "number_of_cuts": 2
}
```

## Running the Code
To execute the implementation, run the following command:
```sh
python script.py
```

This will test the algorithm against multiple test cases and output the results for both memoization and tabulation approaches.

## Test Cases
The script includes several test cases to verify correctness:
1. **Basic Case:** Regular rod cutting scenario.
2. **Optimal No-Cut Case:** Best profit achieved without making any cuts.
3. **Uniform Cuts Case:** The rod is optimally divided into equal pieces.

## Conclusion
This project efficiently solves the **Rod Cutting Problem** using **dynamic programming**. Memoization provides an intuitive recursive solution, while tabulation offers an optimized iterative approach for better performance in large inputs.

