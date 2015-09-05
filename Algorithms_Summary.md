## Algorithms Part 1

### Course Topics
* Vocabulary for design and analysis of algorithms
  * "Big-Oh" notation
  * "sweet spot" for high-level reasoning about algorithms  

* Divide and conquer algorithm design paradigm
  * i.e., integer multplication, sorting, matrix multiplication, closest pair
  * General analysis methods ("Master Method/Theorem")  

* Randomization in algorithm design
  * i.e., Quicksort, primality testing, graph partitioning, hashing  

* Primitives for reasoning about graphs
  * Connectivity information, shortest paths, structure of information and social networks  

* Use and implementation of data structures
  * Heaps, balanced binary search trees, hashing and some variants (e.g., bloom filters)  

### Integer Multiplication

#### Grade-School Algorithm
* **Upshot:** # of operations overall <= `constant (about 4) * n^2`

#### Karatsuba Multiplication

* **Step 1:** compute a * c  
* **Step 2:** compute b * d  
* **Step 3:** compute (a + b) * (c + d)  
* **Step 4:** compute Step 3 - 2 - 1 = ad + bc  

**Example:**  
`x` = 5678, `y` = 1234  
`a` = 56, `b` = 78, `c` = 12, `d` = 34  

* **Upshot:** only need 3 recursive multiplications. (and some additions)

**Recursive Algorithm**  
x = 10^(n/2) * a + b, y = 10^(n/2) * c + d  

**Then:**  
x * y = 10^n * ac + 10^(n/2) * (ad + bc) + bd  

**Idea:**  
Recursively compute ac, ad, bc, bd, then compute the calculation above.  

### Merge Sort
* Good introduction to divide & conquer
  * Improves over Selection, Insertion, Bubble sorts
* Guiding principles (worst-case and asymptotic analysis)
* Analysis generalizes to "Master Method"

**Example:**  
`input` = 54187263  
`a` = 5418, `b` = 7263  

* **Step 1:** recursively sort 1st half of input array
* **Step 2:** recursively sort 2nd half of input array
* **Step 3:** merge two sorted sublists into one

**Merge Steps:**
* C = output[length = n]
* A = 1st sorted array [n/2]
* B = 2nd sorted array [n/2]
* i = 1, j = 1  

* **Upshot:** running time of merge on array of m numbers is <= `4m + 2` <= `6m`
  * since m >= 1

**Claim:**
* Merge Sort requires <= 6n * log2(n) + 6n operations to sort n numbers.
 
**Proof of Claim:**
* total levels from the root = log2(n) + 1 
* at each level j=0,1,2,..,log2(n)
  * 2^j subproblems
  * each of size n/(2^j)

* <= 2^j * 6 * (n/2^j) = 6n <= 6n (log2(n) + 1)
  * work per level * # of levels

#### Guiding Principle

**Principle #1**
* **worst-case analysis:** our running time bound holds for every input of length n
  * as opposed to: "average-case" analysis, benchmarks
    * requires domain knowledge
  * particularly appropriate for "general-purpose" routines  

**Principle #2**
* won't pay much attention to constant factors, lower-order terms
  * way easier
  * constants depend on architecture/compiler/programmer
  * lose very little predictive power  

**Principle #3**
* **Asymptotic analysis:**
  * focus on running time for large input sizes n
  * e.g., 6n * log2(n) + 6n "better than" (1/2) * n^2
    * any big problems are more interesting  

**Fast Algorithm**
* worst-case running time grows slowly with input size
  * mathematical tractability and predictive power
* **Holy Grail:** linear running time