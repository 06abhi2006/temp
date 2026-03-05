# DAA – MSE Important Topics Notes

Based on **IMP TIPS FOR MSE**, Unit-1, Unit-2 and Unit-3 materials.

---

# UNIT 1

## 1. Time Complexity

**Definition**

Time complexity measures how the execution time of an algorithm grows with respect to input size **n**.

It represents the **number of operations performed by an algorithm**.

### Example

```
for(i = 0; i < n; i++)
    sum += i;
```

Time Complexity = **O(n)**

Because the loop executes **n times**.

---

## 2. Space Complexity

**Definition**

Space complexity measures the **total memory used by an algorithm** during execution.

```
Total Space = Input Space + Auxiliary Space
```

### Example

```
int a = 10;
int b = 20;
```

Space Complexity = **O(1)**

Because memory used does not depend on input size.

---

# 3. Classification of Time Complexities

| Complexity | Name | Example |
|---|---|---|
| O(1) | Constant | Access array element |
| O(log n) | Logarithmic | Binary Search |
| O(n) | Linear | Linear Search |
| O(n log n) | Linearithmic | Merge Sort |
| O(n²) | Quadratic | Bubble Sort |
| O(2ⁿ) | Exponential | Recursive Fibonacci |
| O(n!) | Factorial | Traveling Salesman |

### Order of Growth (Fast → Slow)

```
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ) < O(n!)
```

---

# 4. Asymptotic Notations

Asymptotic notations describe **growth rate of algorithms**.

## 4.1 Big-O Notation (Worst Case)

Represents **upper bound** of algorithm complexity.

```
f(n) ≤ c*g(n)
```

### Example

```
f(n) = 2n + 3
```

Dominant term = **n**

```
f(n) = O(n)
```

---

## 4.2 Big-Omega Notation (Best Case)

Represents **lower bound**.

Example – Linear Search

Best case: element found at first position.

```
Ω(1)
```

---

## 4.3 Big-Theta Notation (Average Case)

Represents **tight bound**.

Example

```
f(n) = 6n + 3
```

Dominant term = **n**

```
Θ(n)
```

---

# Graph of Asymptotic Bounds

## Big-O Graph (Upper Bound)

```
Time
 ^
 |           c*g(n)
 |          /
 |         /
 |        /
 |       / 
 |      / f(n)
 |_____/__________________> n
```

f(n) grows **no faster than c*g(n)**.

---

## Big-Omega Graph (Lower Bound)

```
Time
 ^
 |        f(n)
 |       /
 |      /
 |     /
 |    /
 |   / 
 |  / c*g(n)
 |_/____________________> n
```

f(n) grows **at least as fast as c*g(n)**.

---

## Big-Theta Graph (Tight Bound)

```
Time
 ^
 |      c2*g(n)
 |       /
 |      / f(n)
 |     /
 |    /
 |   /
 |  /
 | / 
 |/ c1*g(n)
 +---------------------> n
```

f(n) lies **between two bounds**.

---

# Relationship Between Bounds

```
Ω(f(n)) ≤ Θ(f(n)) ≤ O(f(n))
```

Meaning:

```
Best Case ≤ Average Case ≤ Worst Case
```

---

# 5. Best Case, Worst Case, Average Case

| Case | Meaning | Notation |
|---|---|---|
| Best Case | Minimum execution time | Ω |
| Worst Case | Maximum execution time | O |
| Average Case | Expected execution time | Θ |

### Example: Linear Search

Best Case

```
Ω(1)
```

Worst Case

```
O(n)
```

Average Case

```
Θ(n)
```

---

# UNIT 2

# 1. Complexity Classes

Complexity classes classify problems based on computational difficulty.

```
P ⊆ NP ⊆ NP-Hard
       ↑
   NP-Complete
```

---

# 2. Polynomial Problems

Problems solvable in polynomial time.

```
O(n), O(n²), O(n³)
```

### Examples

- Binary Search
- Merge Sort
- BFS
- DFS

---

# 3. Non-Polynomial Problems

Problems requiring exponential or factorial time.

Examples

- Traveling Salesman Problem
- Recursive Fibonacci
- Boolean Satisfiability (SAT)

---

# 4. Tractable Problems

Problems that can be solved efficiently.

```
Time Complexity ≤ O(n^k)
```

Examples

- Sorting
- Searching
- Shortest path

---

# 5. Intractable Problems

Problems that cannot be solved efficiently.

Examples

- Traveling Salesman Problem
- Knapsack (brute force)

---

# 6. Deterministic Algorithms

Definition:

Algorithm where each step is uniquely defined.

Same input → same output.

### Examples

- Binary Search
- Merge Sort
- Linear Search

---

# 7. Non-Deterministic Algorithms

Algorithms that can choose from multiple possible paths.

Used mainly in **NP problems**.

Example

- Guess solution and verify.

---

# Binary Search Algorithm

Binary search works on **sorted arrays**.

## Algorithm

```
BinarySearch(A, n, key)

1. low = 0
2. high = n - 1

3. while low <= high
4.     mid = (low + high) / 2

5.     if A[mid] == key
6.         return mid

7.     else if key < A[mid]
8.         high = mid - 1

9.     else
10.        low = mid + 1

11. return -1
```

### Time Complexity

```
T(n) = T(n/2) + O(1)
```

```
O(log n)
```

---

# Merge Sort Algorithm

Merge sort uses **Divide and Conquer strategy**.

### Steps

1. Divide array into two halves  
2. Sort both halves recursively  
3. Merge sorted halves  

---

## Algorithm

```
MergeSort(A, l, r)

if l < r
    mid = (l + r) / 2

    MergeSort(A, l, mid)
    MergeSort(A, mid + 1, r)

    Merge(A, l, mid, r)
```

### Time Complexity

```
T(n) = 2T(n/2) + n
```

Using Master Theorem

```
O(n log n)
```

---

# UNIT 3

# Divide and Conquer Strategy

Divide and Conquer is a method where a problem is:

1. Divided into smaller subproblems  
2. Solved recursively  
3. Combined to obtain the final result  

### General Formula

```
T(n) = aT(n/b) + f(n)
```

Where

- **a** = number of subproblems  
- **b** = size reduction factor  
- **f(n)** = cost of dividing and combining  

### Examples

- Binary Search
- Merge Sort
- Quick Sort

---

# Greedy Algorithm

Greedy algorithm selects **best local choice at each step**.

Goal: obtain optimal solution.

### General Greedy Structure

```
S = ∅

while solution not complete
    choose best element
    if feasible
        add to solution
```

---

# Fractional Knapsack Problem

## Problem

Given:

```
n items
weight = wi
profit = pi
capacity = M
```

Goal:

```
Maximize profit
```

---

## Greedy Algorithm

1. Calculate ratio

```
pi / wi
```

2. Sort items in decreasing ratio

3. Fill knapsack

- Take whole item if possible  
- Otherwise take fraction

4. Stop when capacity is full.

---

## Time Complexity

```
O(n log n)
```

(due to sorting)

---

# Job Scheduling Problem

Goal: maximize profit with deadlines.

### Steps

1. Sort jobs by profit (descending)  
2. Assign job to latest available slot before deadline  
3. Continue until all slots are filled  

---

# MOST EXPECTED MSE QUESTIONS

1. Define Time Complexity and Space Complexity  
2. Classification of Time Complexities  
3. Explain Big-O, Omega and Theta  
4. Best Case, Worst Case, Average Case  
5. Polynomial vs Non-Polynomial problems  
6. Complexity classes (P, NP, NP-Complete, NP-Hard)  
7. Binary Search algorithm with complexity  
8. Merge Sort algorithm with recurrence  
9. Divide and Conquer method  
10. Fractional Knapsack problem  
11. Job Scheduling using Greedy method
