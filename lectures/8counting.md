# Counting

**based on:** [https://people.cs.pitt.edu/~milos/courses/cs441/](https://people.cs.pitt.edu/~milos/courses/cs441/)

*prepared by using DeepSeek-r1*

bu ders counting1.pdf-counting2.pdf counting3.pdf slidelardan islendi

---

## Counting  
- Assume we have a set of objects with certain properties.  
- **Counting** is used to determine the number of these objects.  

### Examples:
- Number of available phone numbers with 7 digits in the local calling area.  
- Number of possible starters (football, basketball) given the number of team members and their positions.  

---

## Basic Counting Rules  
- Counting problems may be very hard or not obvious.  
- **Solution**: Simplify the problem by decomposing it.

### Two basic decomposition rules:
1. **Product Rule**: A count decomposes into a sequence of dependent counts ("each element in the first count is associated with all elements of the second count").  
2. **Sum Rule**: A count decomposes into a set of independent counts ("elements of counts are alternatives").  

---

## Product Rule  
- **Definition**: A count can be broken down into a sequence of dependent counts ("each element in the first count is associated with all elements of the second count").  

### Example:
- **Scenario**: an auditorium with seats labeled by a letter and numbers (e.g., A23).  
  - 26 letters and 50 numbers.  
  - Total seats = `26 * 50 = 1300`.  

### Formula:  
- If a count of elements can be broken into a sequence of dependent counts:
  \[
  n = n_1 \times n_2 \times \dots \times n_k
  \]  

---

## Product Rule Application  
### Example 1:  
- **Problem**: How many different bit strings of length 7 are there?  
  - Each bit has 2 possibilities (0 or 1).  
  - Total = `2^7 = 128`.  

### Example 2:  
- **Problem**: The number of subsets of a set \( S \) with \( k \) elements.  
  - Using bitstring representation (1 if an element is in the subset, 0 otherwise).  
  - Total subsets = `2^k`.  

---

## Sum Rule  
- **Definition**: A count decomposes into a set of independent counts ("elements of counts are alternatives").  

### Example:
- Travel between cities A and B:  
  - 12 flights, 5 trains, 10 buses.  
  - Total = `12 + 5 + 10 = 27`.  

### Formula:
- If a count is broken into independent counts:
  \[
  n = n_1 + n_2 + \dots + n_k
  \]  

---

## Beyond Basic Counting Rules  

### Complex Problem Example: Passwords  
- **Problem**: A password of length 6 to 8 with uppercase letters and digits, requiring at least one digit.  
1. Use the **Sum Rule**:  
   \( P = P_6 + P_7 + P_8 \)  
2. Use the **Product Rule**:
   - \( P_{\text{6-all}} = 36^6 \)  
   - \( P_{\text{6-no-digits}} = 26^6 \)  
   - \( P_{\text{6-digits}} = P_{\text{6-all}} - P_{\text{6-no-digits}} \)  

---

### Final Calculation:
- \( P_6 = 36^6 - 26^6 \)  
- \( P_7 = 36^7 - 26^7 \)  
- \( P_8 = 36^8 - 26^8 \)  
- Total passwords:
  \[
  P = P_6 + P_7 + P_8
  \]  

---

## Inclusion-Exclusion Principle  
- Handles overlapping counts where applying the sum rule would result in double-counting.  

### Principle:
\[
|A \cup B| = |A| + |B| - |A \cap B|
\]  

### Example:
- **Problem**: Bitstrings of length 8 starting with 1 or ending with 00.  
  - Start with 1: \( 2^7 \)  
  - End with 00: \( 2^6 \)  
  - Start with 1 **and** end with 00: \( 2^5 \)  
  - Total = \( 2^7 + 2^6 - 2^5 = 128 + 64 - 32 = 160 \).  

---

## Tree Diagrams  
- Use a tree structure to represent counting problems and alternatives.  
- Each leaf node corresponds to a final count.  

### Example:
- Bitstrings of length 4 with no two consecutive ones.  
  - Build a tree and count valid configurations.  

---


### Tree Diagram: Bitstrings of Length 4 with No Two Consecutive Ones

**Legend:**  
- **Nodes:** Represent bit positions (1st, 2nd, 3rd, 4th).  
- **Branches:** Choices for each bit (`0` or `1`), avoiding consecutive `1`s.  
- **Leaves:** Valid 4-bit strings (total **8**).

---

### Diagram Structure

```
Root (Start)
├─ 0 (1st bit)
│  ├─ 0 (2nd bit)
│  │  ├─ 0 (3rd bit)
│  │  │  ├─ 0 (4th bit) → **0000**
│  │  │  └─ 1 (4th bit) → **0001**
│  │  └─ 1 (3rd bit)
│  │     └─ 0 (4th bit) → **0010**
│  └─ 1 (2nd bit)
│     └─ 0 (3rd bit)
│        ├─ 0 (4th bit) → **0100**
│        └─ 1 (4th bit) → **0101**
└─ 1 (1st bit)
   └─ 0 (2nd bit)
      ├─ 0 (3rd bit)
      │  ├─ 0 (4th bit) → **1000**
      │  └─ 1 (4th bit) → **1001**
      └─ 1 (3rd bit)
         └─ 0 (4th bit) → **1010**
```

---

## Valid Bitstrings (Leaf Nodes)
1. `0000`
2. `0001`
3. `0010`
4. `0100`
5. `0101`
6. `1000`
7. `1001`
8. `1010`

---

## Key Observations
- **Rule:** If a `1` is chosen, the next bit must be `0`.  
- **Total Valid Configurations:** 8 (matches the Fibonacci recurrence: \( F(4+2) = F(6) = 8 \)).  

**Formula:**  
For bitstrings of length \( n \), the count is \( F(n+2) \), where \( F \) is the Fibonacci sequence.  

---


## Pigeonhole Principle  
- **Definition**: If there are more objects than bins, then at least one bin has more than one object.  

### Example 1:  
- 7 balls and 5 bins => at least one bin has more than 1 ball.  

### Theorem:
- If there are \( k+1 \) objects and \( k \) bins, at least one bin has 2 or more objects.  

---

## Generalized Pigeonhole Principle  
**Theorem**:  
- If \( N \) objects are placed into \( k \) bins, at least one bin contains at least \( \lceil N / k \rceil \) objects.  

### Example:
- 100 people and 12 months:  
  - \( \lceil 100 / 12 \rceil = 9 \)  
  - At least 9 people share the same birth month.  

---

# lecture 2

---

# Counting

- Assume we have a set of **objects with certain properties**.
- **Counting** is used to determine the **number of these objects**.

## Examples:
- Number of available phone numbers with 7 digits in the local calling area.
- Number of possible match starters (football, basketball) given the number of team members and their positions.

---

# Basic Counting Rules

- Counting problems may be hard, and easy solutions are not obvious.
- **Approach:** Simplify the solution by decomposing the problem.

## Two Basic Decomposition Rules:
1. **Product Rule**  
   - A count decomposes into a sequence of dependent counts.  
   - *Example:* Choosing a meal with 3 appetizers and 4 main courses → \(3 \times 4 = 12\) options.
2. **Sum Rule**  
   - A count decomposes into a set of independent counts (alternatives).  
   - *Example:* Choosing between 5 salads *or* 3 soups → \(5 + 3 = 8\) options.

---

# Inclusion-Exclusion Principle

**Used when counts overlap.**  
If sets \(A\) and \(B\) overlap, the total count is:  
\[
|A \cup B| = |A| + |B| - |A \cap B|
\]

### Example:
How many bitstrings of length 8 start with 1 **or** end with 00?  
- Start with 1: \(2^7 = 128\)  
- End with 00: \(2^6 = 64\)  
- Overlap (start with 1 **and** end with 00): \(2^5 = 32\)  
- Total: \(128 + 64 - 32 = 160\).

---

# Pigeonhole Principle

- If \(N\) objects are placed into \(k\) bins, then at least one bin contains at least \(\lceil N/k \rceil\) objects.

### Example:
- 100 people → At least \(\lceil 100/12 \rceil = 9\) people share a birth month.

---

# Permutations

A **permutation** is an *ordered arrangement* of distinct objects.  
Number of permutations of \(n\) elements:  
\[
P(n, n) = n!
\]

### Example:
Permutations of \(\{a, b, c\}\):  
\(abc, acb, bac, bca, cab, cba\) → \(3! = 6\).

---

# \(k\)-Permutations

An ordered arrangement of \(k\) elements from a set of \(n\).  
Formula:  
\[
P(n, k) = \frac{n!}{(n - k)!}
\]

### Example:
Medals for 8 runners (gold, silver, bronze):  
\(P(8, 3) = 8 \times 7 \times 6 = 336\).

---

# Combinations

A **\(k\)-combination** is an *unordered* selection of \(k\) elements.  
Formula:  
\[
C(n, k) = \binom{n}{k} = \frac{n!}{k!(n - k)!}
\]

### Example:
Teams of 5 from 10 members:  
\[
\binom{10}{5} = \frac{10!}{5!5!} = 252
\]

### Properties:
- \(\binom{n}{k} = \binom{n}{n - k}\)  
- \(\binom{n}{0} = \binom{n}{n} = 1\)

---

# Binomial Theorem

Expanding \((a + b)^n\):  
\[
(a + b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k
\]

### Example:
\[
(a + b)^3 = \binom{3}{0}a^3 + \binom{3}{1}a^2b + \binom{3}{2}ab^2 + \binom{3}{3}b^3 = a^3 + 3a^2b + 3ab^2 + b^3
\]

---

## **Combinations** (Deep Dive)
A **k-combination** is an unordered selection of *k* elements from a set of *n* distinct elements.  
**Formula:**  
\[
C(n, k) = \binom{n}{k} = \frac{n!}{k!(n - k)!}
\]

---

### **Key Properties**
1. **Symmetry:** \(\binom{n}{k} = \binom{n}{n - k}\)  
   - *Example:* \(\binom{10}{3} = \binom{10}{7} = 120\)
2. **Boundary Cases:** \(\binom{n}{0} = \binom{n}{n} = 1\)  
3. **Sum of Combinations:** \(\sum_{k=0}^n \binom{n}{k} = 2^n\) (total subsets of an *n*-element set).

---

### **Extended Examples**
1. **Pizza Toppings**  
   *How many ways to choose 3 toppings from 8?*  
   \[
   \binom{8}{3} = \frac{8!}{3!5!} = 56
   \]

2. **Lottery Numbers**  
   *Choosing 6 numbers out of 49:*  
   \[
   \binom{49}{6} = \frac{49!}{6!43!} = 13,\!983,\!816
   \]

3. **Team Formation**  
   *Selecting 4 people from 7 for a project:*  
   \[
   \binom{7}{4} = \binom{7}{3} = 35 \quad (\text{using symmetry})
   \]

4. **Probability Application**  
   *Flipping a coin 5 times: ways to get exactly 3 heads:*  
   \[
   \binom{5}{3} = 10
   \]

5. **Subsets with Restrictions**  
   *From the word "COMBINE" (7 letters), how many 3-letter subsets include at least 1 vowel (E, I, O)?*  
   - Total subsets: \(\binom{7}{3} = 35\)  
   - Subsets with no vowels (only consonants C, M, B, N): \(\binom{4}{3} = 4\)  
   - Valid subsets: \(35 - 4 = 31\).

---

## **Binomial Coefficients** (Deep Dive)
The binomial coefficient \(\binom{n}{k}\) appears in the expansion of \((a + b)^n\).  

**Binomial Theorem:**  
\[
(a + b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k
\]

---

### **Extended Examples**
1. **Expanding \((x + y)^5\)**  
   \[
   (x + y)^5 = \binom{5}{0}x^5 + \binom{5}{1}x^4y + \binom{5}{2}x^3y^2 + \binom{5}{3}x^2y^3 + \binom{5}{4}xy^4 + \binom{5}{5}y^5
   \]  
   Coefficients: \(1, 5, 10, 10, 5, 1\).

2. **Finding Specific Terms**  
   *What is the coefficient of \(a^2b^3\) in \((a + b)^5\)?*  
   \[
   \binom{5}{3} = 10 \quad (\text{or } \binom{5}{2} = 10 \text{ by symmetry})
   \]

3. **Pascal's Triangle Connection**  
   - Row 5: \(1, 5, 10, 10, 5, 1\)  
   - Each entry is \(\binom{n}{k}\) for \(n = 5\).

4. **Counting Paths**  
   *How many shortest paths from point A to B in a grid (3 right, 2 up)?*  
   \[
   \binom{5}{3} = 10 \quad (\text{choose 3 right moves out of 5 total steps})
   \]

5. **Probability Distribution**  
   In a binomial distribution, \(\binom{n}{k}\) counts the number of ways to get \(k\) successes in \(n\) trials.  
   *Example:* Probability of 3 heads in 5 coin flips:  
   \[
   \binom{5}{3} \left(\frac{1}{2}\right)^5 = 10 \times \frac{1}{32} = \frac{10}{32}
   \]

---

## **Permutations vs. Combinations**
- **Permutations (Order matters):**  
  *Arranging 3 books out of 5 on a shelf:*  
  \[
  P(5, 3) = 5 \times 4 \times 3 = 60
  \]
- **Combinations (Order irrelevant):**  
  *Choosing 3 books to take on a trip:*  
  \[
  \binom{5}{3} = 10
  \]

---

## **Summary Table**
| Concept               | Formula/Example                     | Use Case                     |
|-----------------------|-------------------------------------|------------------------------|
| **Combination**       | \(\binom{10}{5} = 252\)            | Selecting teams, lotteries   |
| **Binomial Expansion**| \((a + b)^4 = a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4\) | Polynomial expansions |
| **Symmetry**          | \(\binom{7}{2} = \binom{7}{5} = 21\) | Simplifying calculations |

---

# lecture-3

---
# Permutations

**Definition:** A permutation of a set of distinct objects is an **ordered arrangement** of the objects.  
**Formula:**  
\[
P(n, n) = n!
\]

## Example:
Permutations of \( S = \{a, b, c\} \):  
\[
abc, \ acb, \ bac, \ bca, \ cab, \ cba \quad (3! = 6)
\]

---

# \(k\)-Permutations

**Definition:** An ordered arrangement of \(k\) elements from a set of \(n\).  
**Formula:**  
\[
P(n, k) = \frac{n!}{(n - k)!}
\]

**Example:**
2-permutations of \(\{a, b, c\}\):  
\[
ab, \ ba, \ ac, \ ca, \ bc, \ cb \quad (P(3, 2) = 6)
\]

---

# Combinations

**Definition:** A \(k\)-combination is an **unordered** selection of \(k\) elements.  
**Formula:**  
\[
C(n, k) = \binom{n}{k} = \frac{n!}{k!(n - k)!}
\]

**Example:**
2-combinations of \(\{a, b, c\}\):  
\[
\{a, b\}, \ \{a, c\}, \ \{b, c\} \quad \left(\binom{3}{2} = 3\right)
\]

---

## Binomial Coefficients

**Binomial Theorem:**  
\[
(a + b)^n = \sum_{k=0}^n \binom{n}{k} a^{n-k} b^k
\]

## Example:
Expansion of \((a + b)^3\):  
\[
a^3 + 3a^2b + 3ab^2 + b^3 \quad (\text{coefficients: } 1, 3, 3, 1)
\]

---

## Key Corollaries:
1. \(\sum_{k=0}^n \binom{n}{k} = 2^n\)  
   *Proof:* Substitute \(a = 1, b = 1\).  
2. \(\sum_{k=0}^n (-1)^k \binom{n}{k} = 0\)  
   *Proof:* Substitute \(a = 1, b = -1\).  

---

## Pascal's Triangle

**Recursive Relation:**  
\[
\binom{n+1}{k} = \binom{n}{k-1} + \binom{n}{k}
\]

## Example:
First 5 rows:  
```
       1
      1 1
     1 2 1
    1 3 3 1
   1 4 6 4 1
```

---


## **Proof (Combinatorial Interpretation)**  
Consider a set \( S \) with \( n+1 \) elements. We want to count the number of subsets of size \( k \).  
- **Case 1:** The subset includes a specific element (e.g., the last element).  
  - We need to choose \( k-1 \) elements from the remaining \( n \) elements:  
    \[
    \binom{n}{k-1}
    \]
- **Case 2:** The subset does not include the specific element.  
  - We choose all \( k \) elements from the remaining \( n \) elements:  
    \[
    \binom{n}{k}
    \]  
- **Total subsets:**  
  \[
  \binom{n}{k-1} + \binom{n}{k} = \binom{n+1}{k}
  \]

---

## **Example (Pascal's Triangle)**  
For \( n = 4, k = 2 \):  
\[
\binom{5}{2} = \binom{4}{1} + \binom{4}{2} = 4 + 6 = 10
\]

---

# Permutations with Repetitions

**Formula:**  
\[
\text{Number of } k\text{-permutations} = n^k
\]

## Example:
Number of 4-letter strings using 26 alphabets:  
\[
26^4 = 456,\!976
\]

---

# Combinations with Repetitions

**Formula:**  
\[
\binom{n + k - 1}{n} \quad \text{(ways to choose \(n\) items from \(k\) types)}
\]

\[
\binom{n + k - 1}{n} \quad \text{or equivalently} \quad \binom{n + k - 1}{k - 1}.
\]

---

## Combinations with Repetitions

**Problem:** Select 4 fruits from 3 types (apples, pears, oranges).  
**Formula:**  
\[
\binom{n + k - 1}{n} = \binom{4 + 3 - 1}{4} = \binom{6}{4} = 15
\]

---

## **Proof with Stars and Bars**  
Represent fruits as stars (`★`) and separators between types as bars (`|`):  
- **Total symbols:** \( n + k - 1 = 4 + 3 - 1 = 6 \) (4 stars + 2 bars).  
- **Arrange stars and bars in 6 positions.**  

### **Examples:**  
1. `★★|★|★` = 2 apples, 1 pear, 1 orange.  
2. `★★★★||` = 4 apples, 0 pears, 0 oranges.  
3. `|★★★|★` = 0 apples, 3 pears, 1 orange.  

---

### **Calculation:**  
- Choose 4 positions for stars (or 2 positions for bars):  
  \[
  \binom{6}{4} = \frac{6!}{4!2!} = 15
  \]

- The formula counts the number of ways to distribute \( n \) identical items into \( k \) distinct categories.

---

## **Why It Works**  
- **Stars** = items selected.  
- **Bars** = dividers between categories.  
- The arrangement `★|★★★` ↔ selecting 1 apple, 3 pears, 0 oranges.  
- **Order of stars/bars does not matter** → equivalent to combinations.

---

# Using Generating Functions To Count Things 

---

## **Introduction to Generating Functions**
- **Definition:** A generating function encodes a sequence \(a_0, a_1, a_2, \dots\) into a formal power series:  
  \[
  G(x) = \sum_{n=0}^{\infty} a_n x^n
  \]
- **Purpose:** Simplify counting problems by translating combinatorial constraints into algebraic operations.

---

the coefficient of $𝑥^𝑟$ in $(1+𝑥)^n$, is $\binom{n}{r}$.
- The generating function for bioniamial coefficients is
\[
(1+𝑥)^n
\]
The coefficient of $x^r$ is the number of ways of choosing the 𝑥 from 𝑟 of the 𝑛 factors

---

The grocery store sells paper plates in packages of 1, 5, 20, or 75. In how many different ways can we buy a total of 95 paper plates?
- the coefficient of $𝑥^𝑛$ will represent the number of ways in which we can buy 𝑛 paper plates

---

Buying 1-paper plates;
\[
1 + x + x^2 + x^3 + x^4 + . . . = \sum_{i=0}^{\infty} x^i = \dfrac{1}{(1-x)}
\]

---

Buying 5-paper plates;
\[
1 + x^5 + x^{10} + x^{15} + x^{20} + . . . = \sum_{i=0}^{\infty} x^{5i} = \dfrac{1}{(1-x^5)}
\]

---

The generating function:
\[
(1 + x + x^2 + . . . + x^{95})(1 + x^5 + x^{10} + . . . + x^{95})(1 + x^{20} + x^{40} + x^{60} + x^{80})(1 + x^{75})
\]
- we are looking for the coefficient of $x^{95}$.

---
For any positive integer $k$;

\[
1 + x + x^2 + · · · + x^k = \dfrac{1-x^{k+1}}{1-x}
\]

---

## Counting Coin Combinations with Generating Functions

**Problem:** Count the number of ways to make \( n \) cents using pennies (1¢) and nickels (5¢).

---

## **Step 1: Define Generating Functions**
### **Pennies (1¢)**  
- Can use 0, 1, 2, 3, ... pennies.  
- Generating function:  
  \[
  G_{\text{penny}}(x) = 1 + x + x^2 + x^3 + \cdots = \frac{1}{1-x}
  \]  
  *(Geometric series for unlimited 1¢ choices)*  

### **Nickels (5¢)**  
- Can use 0, 1, 2, 3, ... nickels.  
- Generating function:  
  \[
  G_{\text{nickel}}(x) = 1 + x^5 + x^{10} + x^{15} + \cdots = \frac{1}{1-x^5}
  \]  
  *(Geometric series for 5¢ increments)*  

---

## **Step 2: Combine Generating Functions**  
- Total ways to combine pennies and nickels:  
  \[
  G(x) = G_{\text{penny}}(x) \cdot G_{\text{nickel}}(x) = \frac{1}{(1-x)(1-x^5)}
  \]  
- **Key Insight:** The coefficient of \( x^n \) in \( G(x) \) gives the number of ways to make \( n \) cents.  

---

## **Step 3: Example Calculation**  
### **For \( n = 6 \) cents:**  
Expand \( G(x) \):  
\[
(1 + x + x^2 + x^3 + x^4 + x^5 + x^6 + \cdots)(1 + x^5 + x^{10} + \cdots)
\]  
- **Ways to make 6¢:**  
  - **0 nickels + 6 pennies:** \( x^6 \cdot 1 = x^6 \)  
  - **1 nickel + 1 penny:** \( x^5 \cdot x^1 = x^6 \)  
- **Total:** Coefficient of \( x^6 = 2 \) → **2 ways**.  

### **For \( n = 10 \) cents:**  
- **0 nickels + 10 pennies:** \( x^{10} \cdot 1 \)  
- **1 nickel + 5 pennies:** \( x^5 \cdot x^5 \)  
- **2 nickels + 0 pennies:** \( x^{10} \cdot 1 \)  
- **Total:** Coefficient of \( x^{10} = 3 \) → **3 ways**.  

---

## **Step 4: General Formula**  
The number of ways to make \( n \) cents is the coefficient of \( x^n \) in:  
\[
\frac{1}{(1-x)(1-x^5)} = \sum_{k=0}^{\infty} \left\lfloor \frac{n}{5} \right\rfloor + 1 \quad \text{(for \( n \geq 0 \))}
\]  
**Interpretation:** For every 5¢ increment (nickel), add 1 way.  

---

## **Summary**  
1. **Generating Functions** model unlimited choices per coin type.  
2. **Multiplication** of series corresponds to combining choices.  
3. **Coefficients** directly count valid combinations.  

**Example Answer:**  
For \( n = 6 \) cents, there are **2 ways**:  
- 6 pennies, or  
- 1 nickel + 1 penny.  

---


## **Basic Examples**
### **Example: Coin Selection**
- **Problem:** Count ways to choose coins (pennies, nickels).  
- **Generating Functions:**  
  - Penny: \(1 + x + x^2 + \cdots = \frac{1}{1-x}\)  
  - Nickel: \(1 + x^5 + x^{10} + \cdots = \frac{1}{1-x^5}\)  
- **Combined:**  
  \[
  G(x) = \frac{1}{(1-x)(1-x^5)}
  \]

---

### **Example: Binary Strings**  
- **Problem:** Count binary strings of length \(n\).  
- **Generating Function:**  
  \[
  G(x) = (1 + x)^n \quad \text{(each bit: 0 or 1)}
  \]

---

A binary string can consist of the characters '0' and '1'. 

**Step 1: Define the Generating Function**

Let \( a_n \) be the number of binary strings of length \( n \). 
For each position in the string, we have 2 choices: either '0' or '1'. Therefore, the number of binary strings of length \( n \) can be expressed as:

\[
a_n = 2^n
\]

---

**Step 2: Construct the Generating Function**

The generating function \( A(x) \) for the sequence \( a_n \) is defined as:

\[
G(x) = \sum_{n=0}^{\infty} a_n x^n
\]

Substituting \( a_n = 2^n \):

\[
G(x) = \sum_{n=0}^{\infty} 2^n x^n
\]

---

**Step 3: Recognize the Series**

The series \( \sum_{n=0}^{\infty} (2x)^n \) is a geometric series with the first term \( 1 \) and common ratio \( 2x \). The sum of a geometric series can be expressed as:

\[
\sum_{n=0}^{\infty} r^n = \frac{1}{1 - r} \quad \text{for } |r| < 1
\]

In our case, \( r = 2x \). Thus, we have:

\[
G(x) = \frac{1}{1 - 2x} \quad \text{for } |2x| < 1 \quad \text{or } |x| < \frac{1}{2}
\]

---

**Conclusion**

The generating function for the number of binary strings of length \( n \) is:

\[
G(x) = \frac{1}{1 - 2x}
\]

This generating function can be used to extract coefficients corresponding to the number of binary strings of various lengths. The coefficient of \( x^n \) in the expansion of \( G(x) \) will give us \( a_n = 2^n \).

---

## **Product Rule for Generating Functions**
- **Rule:** If choices are independent, multiply their generating functions.  
- **Example:**  
  - Apples: 0-2 allowed → \(1 + x + x^2\)  
  - Oranges: 0-3 allowed → \(1 + x + x^2 + x^3\)  
  - Total:  
    \[
    G(x) = (1 + x + x^2)(1 + x + x^2 + x^3) = 1 + 2x + 3x^2 + 3x^3 + 2x^4 + x^5
    \]
  - **Interpretation:** Coefficient of \(x^k\) = number of ways to choose \(k\) fruits.

---

## **Solving Combinatorial Problems**
### **Example: Distributing Identical Objects**
- **Problem:** Distribute \(n\) identical balls into 3 boxes (each box holds 0-2 balls).  
- **Generating Function per Box:** \(1 + x + x^2\)  
- **Total Generating Function:**  
  \[
  G(x) = (1 + x + x^2)^3 = 1 + 3x + 6x^2 + 7x^3 + 6x^4 + 3x^5 + x^6
  \]
- **Coefficient of \(x^3\):** 7 ways to distribute 3 balls.

---

## **Advanced Application: Recurrence Relations**
### **Fibonacci Sequence**
- **Recurrence:** \(F(n) = F(n-1) + F(n-2)\), with \(F(0)=0, F(1)=1\).  
- **Generating Function:**  
  \[
  G(x) = \frac{x}{1 - x - x^2}
  \]
- **Expansion:** Coefficients yield \(F(n)\).

---

## **Summary**
1. **Generating Functions** encode sequences into polynomials/series.  
2. **Product Rule:** Multiply functions for independent choices.  
3. **Coefficients** solve counting problems (e.g., distributions, selections).  
4. **Applications:** Coin change, string counting, recurrence relations.

---


# Exercises: Combinations with Repetitions

### **Exercise 1**  
How many ways are there to select **5 fruits** from **3 types** (apples, oranges, bananas)?

---

### **Exercise 2**  
A bakery allows customers to choose **7 pastries** from **4 types** (croissants, muffins, cookies, donuts). How many different selections are possible?

---

### **Exercise 3**  
You need to distribute **10 identical coins** into **5 distinct wallets**. How many ways can this be done?

---

### **Exercise 4**  
How many non-negative integer solutions exist for the equation:  
\[
x_1 + x_2 + x_3 = 6 \quad \text{where } x_i \geq 0?
\]

---

### **Exercise 5**  
Visualize the selection of **3 drinks** from **2 types** (coffee, tea) using stars and bars. List all possible combinations.

---

### **Exercise 6**  
How many ways can you choose **0 items** from **5 types**? Explain why.

---

---

# Answers

---

### **Answer 1**  
\[
\binom{5 + 3 - 1}{5} = \binom{7}{5} = 21 \quad \text{ways}.
\]

---

### **Answer 2**  
\[
\binom{7 + 4 - 1}{7} = \binom{10}{7} = 120 \quad \text{selections}.
\]

---

### **Answer 3**  
\[
\binom{10 + 5 - 1}{10} = \binom{14}{10} = 1001 \quad \text{ways}.
\]

---

### **Answer 4**  
\[
\binom{6 + 3 - 1}{6} = \binom{8}{6} = 28 \quad \text{solutions}.
\]

The number of non-negative integer solutions to the equation \( x_1 + x_2 + x_3 = 6 \) (where \( x_i \geq 0 \)) is **28**.  

### **Explanation**  
We use the **stars and bars** combinatorial method:  
1. Represent the equation as distributing **6 identical "stars"** (\( \star \)) into **3 distinct groups** (for \( x_1, x_2, x_3 \)), separated by **2 bars** (\( | \)).  
   - Example: \( \star\star|\star\star\star|\star \) represents \( x_1 = 2 \), \( x_2 = 3 \), \( x_3 = 1 \).  

2. Total symbols = \( 6 \, \text{stars} + 2 \, \text{bars} = 8 \).  
3. The number of ways to arrange these symbols is the number of ways to choose positions for the **2 bars** (or equivalently, the **6 stars**):  
   \[
   \binom{8}{2} = \frac{8!}{2!6!} = 28.
   \]


---

### **Answer 5**  
**Stars and Bars Notation:**  
- `★★★|` = 3 coffee, 0 tea.  
- `★★|★` = 2 coffee, 1 tea.  
- `★|★★` = 1 coffee, 2 tea.  
- `|★★★` = 0 coffee, 3 tea.  
Total: \(\binom{3 + 2 - 1}{3} = \binom{4}{3} = 4\) ways.

---

### **Answer 6**  
\[
\binom{0 + 5 - 1}{0} = \binom{4}{0} = 1 \quad \text{way}.
\]  
*Explanation:* There is exactly one way to choose nothing from any set.

---
