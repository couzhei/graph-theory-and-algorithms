# Proof of Correctness and Efficiency: Recursive Selection Sort

## Algorithm Overview

The algorithm consists of two recursive functions:

```python
def prefix_max(A, i):
    """Returns the index of maximum value in A[0..i] (inclusive)."""
    if i > 0:
        j = prefix_max(A, i - 1)
        if A[i] < A[j]:
            return j
    return i

def selection_sort(A, i=None):
    """Sorts A in place using selection sort algorithm."""
    if i is None: i = len(A) - 1
    if i > 0:
        j = prefix_max(A, i)
        A[i], A[j] = A[j], A[i]
        selection_sort(A, i - 1)
```

---

## Part 1: Proof of Correctness

### Correctness of `prefix_max(A, i)`

**Claim:** `prefix_max(A, i)` returns the index of the maximum element in A[0..i].

**Proof by Strong Induction on i:**

**Base Case (i = 0):**

- The function returns 0 without entering the if block
- A[0] is trivially the maximum of a single-element subarray A[0..0]
- ✓ Base case holds

**Inductive Step:**

- **Inductive Hypothesis:** Assume `prefix_max(A, k)` correctly returns the index of the maximum element in A[0..k] for all k < i

- **For i > 0:**
  - The function calls `prefix_max(A, i-1)` and gets index j
  - By IH, j is the index of max(A[0..i-1])
  - The function then compares A[i] with A[j]:
    - If A[i] < A[j]: returns j (max of A[0..i-1] is overall max) ✓
    - If A[i] ≥ A[j]: returns i (A[i] is the overall max) ✓
  - In both cases, the returned index points to max(A[0..i])

**Conclusion:** By mathematical induction, `prefix_max(A, i)` is correct for all i ≥ 0. □

---

### Correctness of `selection_sort(A, i)`

**Claim:** `selection_sort(A, i)` sorts A[0..i] in non-decreasing order.

**Proof by Strong Induction on i:**

**Base Case (i = 0):**

- A single element is trivially sorted
- ✓ Base case holds

**Inductive Step:**

- **Inductive Hypothesis:** Assume `selection_sort(A, k)` correctly sorts A[0..k] for all k < i

- **For i > 0:**

  1. Find j = `prefix_max(A, i)` (index of max element in A[0..i])
  2. Swap A[i] ↔ A[j]
     - After swap: A[i] contains max(A[0..i])
     - Property: A[i] ≥ A[k] for all k ∈ [0, i-1]
  3. Recursively call `selection_sort(A, i-1)`
     - By IH, this correctly sorts A[0..i-1]

  - **Result:** A[0..i-1] is sorted AND A[i] ≥ all elements in A[0..i-1]
  - Therefore, A[0..i] is sorted in non-decreasing order ✓

**Conclusion:** By mathematical induction, `selection_sort(A, i)` correctly sorts A[0..i] for all i ≥ 0. □

---

## Part 2: Efficiency Analysis

### Time Complexity

#### Analysis of `prefix_max(A, i)`

**Recurrence Relation:**

- $T_{\text{prefix}}(i) = T_{\text{prefix}}(i-1) + O(1) \quad \text{for} \quad i > 0$
- $T_{\text{prefix}}(0) = O(1)$

**Solution:**

$$
\begin{align}
T_{\text{prefix}}(i) &= \underbrace{O(1) + O(1) + \cdots + O(1)}_{i+1 \text{ times}} \\
&= O(i)
\end{align}
$$

#### Analysis of `selection_sort(A, i)`

**Recurrence Relation:**

- $T_{\text{sort}}(i) = T_{\text{prefix}}(i) + T_{\text{sort}}(i-1) + O(1) \quad \text{for} \quad i > 0$
- $T_{\text{sort}}(0) = O(1)$

Substituting $T_{\text{prefix}}(i) = O(i)$:

$$T_{\text{sort}}(i) = O(i) + T_{\text{sort}}(i-1) + O(1)$$

**Expanding the recurrence:**

$$
\begin{align}
T_{\text{sort}}(n) &= O(n) + O(n-1) + O(n-2) + \cdots + O(1) \\
&= O(n + (n-1) + (n-2) + \cdots + 1) \\
&= O\left(\frac{n(n+1)}{2}\right) \\
&= O(n^2)
\end{align}
$$

**By Summation Formula:**
$$\sum_{i=1}^{n} i = \frac{n(n+1)}{2} = \Theta(n^2)$$

**Time Complexity: O(n²)**

#### Detailed Execution Example

For array of size n=6:

- Level 1: `prefix_max(A, 6)` → 6 comparisons
- Level 2: `prefix_max(A, 5)` → 5 comparisons
- Level 3: `prefix_max(A, 4)` → 4 comparisons
- Level 4: `prefix_max(A, 3)` → 3 comparisons
- Level 5: `prefix_max(A, 2)` → 2 comparisons
- Level 6: `prefix_max(A, 1)` → 1 comparison

**Total:** 6 + 5 + 4 + 3 + 2 + 1 = 21 = 6×7/2 comparisons

---

### Space Complexity

**Call Stack Analysis:**

1. **`selection_sort` recursion depth:** $O(n)$

   - Calls: $\text{selection\_sort}(n) \to \text{selection\_sort}(n-1) \to \cdots \to \text{selection\_sort}(0)$
   - Maximum stack depth: $n$

2. **`prefix_max` recursion depth:** $O(n)$
   - At each level of `selection_sort`, `prefix_max` recurses up to depth $i$
   - Maximum accumulated depth: when `selection_sort` calls $\text{prefix\_max}(n-1)$
   - This adds $O(n)$ to the stack

**Total Stack Space: $O(n)$**

**Auxiliary Space: $O(1)$** (only uses loop variables, no additional arrays)

**Space Complexity: $O(n)$** (due to recursive call stack)

---

## Summary Table

| Metric               | Value          | Notes                                      |
| -------------------- | -------------- | ------------------------------------------ |
| **Time Complexity**  | **O(n²)**      | Θ(n²) - same for all cases                 |
| **Space Complexity** | **$O(n)$**     | Recursive call stack                       |
| **Comparisons**      | **$n(n-1)/2$** | Exact count: sum from 1 to n-1             |
| **Swaps**            | **$≤ n$**      | At most one per level                      |
| **In-place**         | **Yes**        | Modifies input array                       |
| **Stable**           | **No**         | May reverse order of equal elements        |
| **Adaptive**         | **No**         | Same performance regardless of input order |

---

## Comparison with Iterative Selection Sort

**Recursive version:**

- Time: $O(n^2)$
- Space: $O(n)$ - call stack overhead

**Iterative version:**

```python
def selection_sort_iterative(A):
    for i in range(len(A)-1, 0, -1):
        j = 0
        for k in range(1, i+1):
            if A[k] > A[j]:
                j = k
        A[i], A[j] = A[j], A[i]
```

- Time: $O(n^2)$
- Space: $O(1)$ - no recursion

**Trade-off:** Recursive version is more elegant but uses $O(n)$ extra space for the call stack.

---

## Conclusion

✓ **Correctness:** Proven by strong mathematical induction for both helper and main functions

✓ **Time Efficiency:** $O(n^2)$ - typical for comparison-based selection sort

✓ **Space Efficiency:** $O(n)$ due to recursive implementation; can be reduced to $O(1)$ with iteration

The algorithm is correct for all valid inputs and has optimal time complexity for the selection sort approach, though merge sort or quicksort can achieve $O(n \log n)$ average time.
