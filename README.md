# 🔍 Searching in C++
# 🎯 Aim
To study and implement Searching algorithms in C++, including Linear Search, Binary Search, Jump Search, Interpolation Search, and Fibonacci Search, and to compare their efficiency, time complexity, and use cases.

# 📚 Theory
Searching is the process of finding the location of a given element (called the key) in a collection of data.

# 1. Linear Search
Traverses the array sequentially from the first element to the last.

Works on unsorted or sorted arrays.

Time Complexity: O(n)
# 2. Binary Search

Works only on sorted arrays.

Repeatedly divides the search interval in half.

Time Complexity: O(log n)
# 3. Jump Search

Works on sorted arrays.

Instead of checking every element, it jumps ahead by fixed steps (√n).

Once the block is found, it performs a linear search inside the block.

Time Complexity: O(√n)
# 4. Interpolation Search

Works on sorted and uniformly distributed arrays.

Improves on binary search by estimating the position of the key using interpolation formula:

pos = low + ((key - arr[low]) * (high - low)) / (arr[high] - arr[low])

Time Complexity: O(log log n) (best case), O(n) (worst case if distribution is skewed).

# 5. Fibonacci Search

Works on sorted arrays.

Uses Fibonacci numbers to divide the array into sections.

Similar to binary search but uses Fibonacci sequence to determine mid.

Time Complexity: O(log n)

# 📋 Algorithms

# 🧾 Linear Search

    Start
    Input array and key.
    For each element from index 0 to n-1:
    If arr[i] == key, return index.
    If not found, print "Element not found".
    End
# 🧾 Binary Search
    Start
    Input sorted array and key.
    Initialize low = 0, high = n-1.
    While low <= high:
    mid = (low + high) / 2
    If arr[mid] == key, return index.
    Else if arr[mid] > key, set high = mid - 1.
    Else set low = mid + 1.
    If not found, print "Element not found".
    End

# 🧾 Jump Search
    Start
    Input sorted array and key.
    Set step = √n.
    Jump ahead in steps until arr[min(step, n)-1] >= key.
    Perform linear search in the block from step/prev to step.
    If found, return index; else print "Element not found".
    End
# 🧾 Interpolation Search
    Start
    Input sorted, uniformly distributed array and key.
    Initialize low = 0, high = n-1.
    While low <= high and key >= arr[low] and key <= arr[high]:
    Compute pos = low + ((key - arr[low]) * (high - low)) / (arr[high] - arr[low]).
    If arr[pos] == key, return index.
    Else if arr[pos] < key, set low = pos + 1.
    Else set high = pos - 1.
    If not found, print "Element not found".
    End
# 🧾 Fibonacci Search
    Start
    Input sorted array and key.
    Initialize Fibonacci numbers: fibM = fib(k), fibMm1 = fib(k-1), fibMm2 = fib(k-2).
    While fibM < n, generate next Fibonacci number.
    Set offset = -1.
    While fibM > 1:
    i = min(offset + fibMm2, n-1)
    If arr[i] < key: shift Fibonacci numbers down by one, set offset = i.
    Else if arr[i] > key: shift Fibonacci numbers down by two.
    Else return index.
    If last element matches key, return index.
    Else print "Element not found".
    End

# 🚀 Applications
    Linear Search → Small or unsorted datasets.
    Binary Search → Large sorted datasets.
    Jump Search → Sorted datasets where √n comparisons are acceptable.
    Interpolation Search → Sorted, uniformly distributed datasets (e.g., phonebooks).
    Fibonacci Search → Sorted datasets where division is costly (uses addition/subtraction).
# 🧠 Conclusion
    Linear Search is simple but inefficient for large datasets.
    Binary Search is efficient but requires sorted data.
    Jump Search optimizes search by skipping blocks.
    Interpolation Search is best for uniformly distributed data.
Fibonacci Search is an alternative to binary search that avoids division.
Together, these algorithms form the foundation of searching techniques in DSA and are widely applied in databases, operating systems, and real-time applications.
