# Cloud Resource Allocation Optimizer

This is a C++ program designed to optimize the distribution of tasks across a set of available servers. The primary goal is to **minimize the maximum load** placed on any single server, ensuring an efficient and balanced allocation of resources.

This problem is a classic application of the **Binary Search on Answer** pattern (similar to the Book Allocation Problem).

## 🚀 Features
- **Optimized Performance**: Utilizes Binary Search to efficiently find the optimal maximum load in `O(N log(Sum - Max))` time complexity.
- **Large Input Support**: Implemented using `long long` to prevent integer overflow when dealing with massive task loads.
- **Fast I/O**: Incorporates C++ fast I/O configurations for significant performance boosts during standard input and output.
- **Detailed Strategy Output**: Reconstructs and clearly displays the exact assignment of tasks to each server.

## 🧠 How It Works

The algorithm uses binary search over the possible range of "maximum loads":
1. **Low Bound**: The single largest task in the list (since a server must be able to handle at least the largest single task).
2. **High Bound**: The sum of all tasks (the worst-case scenario where 1 server handles everything).
3. **Validation (`isPossible` function)**: For a guessed maximum load (`mid`), it sequentially assigns tasks to servers. If adding a task exceeds `mid`, a new server is allocated. If the required servers exceed the available servers, the guessed load is too small.

## 💻 How to Run

### Prerequisites
- A C++ compiler (like GCC or Clang)

### Compilation
Open your terminal and compile the program using:
```bash
g++ CloudResourceAllocation.cpp -o CloudResourceAllocation
```

### Execution
Run the compiled executable:
```bash
./CloudResourceAllocation
```

## 📊 Example Usage

**Input:**
```text
Enter the total number of tasks: 4
Enter the load for each task (space-separated): 10 20 30 40
Enter the number of servers available: 2
```

**Output:**
```text
============================================
   Cloud Resource Allocation Optimization   
============================================

Optimal Load Strategy Results:
--------------------------------
>> Optimal Maximum Load Value: 60

Task Allocation Strategy:
Server 1 [Load: 60] -> Tasks assigned: { 10, 20, 30 }
Server 2 [Load: 40] -> Tasks assigned: { 40 }

============================================
Outcome: Efficient scaling and reduced latency achieved!
============================================
```

## ⏱️ Complexity
- **Time Complexity:** `O(N log(S - M))` where `N` is the number of tasks, `S` is the sum of all tasks, and `M` is the maximum single task.
- **Space Complexity:** `O(N)` to store the tasks and the final reconstructed allocation strategy.
