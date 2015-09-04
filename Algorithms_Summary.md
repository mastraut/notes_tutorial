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

### Integer Multiplication

#### Grade-School Algorithm
* **Upshot:** # of operations overall <= `constant (about 4) * n^2`

#### Karatsuba Multiplication
`x` = 5678, `y` = 1234  
`a` = 56, `b` = 78, `c` = 12, `d` = 34  

**Example:**  
* **Step 1:** compute a * c  
* **Step 2:** compute b * d  
* **Step 3:** compute (a + b) * (c + d)  
* **Step 4:** compute Step 3 - 2 - 1 = ad + bc  

* **Upshot:** only need 3 recursive multiplications. (and some additions)

**Recursive Algorithm**  
x = 10^(n/2) * a + b, y = 10^(n/2) * c + d  

**Then:**  
x * y = 10^n * ac + 10^(n/2) * (ad + bc) + bd  

**Idea:**  
recursively compute ac, ad, bc, bd, then compute the calculation above.  
