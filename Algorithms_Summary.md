## Algorithms

### Integer Multiplication

#### Grade-School Algorithm
* **Upshot:** # of operations overall <= constant (about 4) * `n^2`

#### Karatsuba Multiplication
x = 5678
y = 1234

**Example:**
* **Step 1:** compute a * c
* **Step 2:** compute b * d
* **Step 3:** compute (a + b) * (c + d)
* **Step 4:** compute Step 3 - 2 - 1