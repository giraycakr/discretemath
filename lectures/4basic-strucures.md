---
title: "Discrete Mathematics - basic structures"
author: "Ammar Daskin"
theme: black

---

<style type="text/css">
div {
  font-size: clamp(11px, 3vw, 28px);
}
</style>

# Basic Structures: Sets, Functions, Matrices  

---

## Set Theory  
> **Core Idea**: Everything in mathematics (numbers, functions, etc.) can be defined in terms of sets.  
> - If sets behave consistently, so does everything built on them.  
> - **Analogy**:  
>   - Predicate logic = Machine code  
>   - Set theory = Assembly language  

---

### Set Membership ($\in$)  
**Key Predicate**: The **membership** relation $x \in S$ ("$x$ is an element of $S$").  
- A set $S$ is **uniquely defined** by its elements.  
- All set operations can be derived from $\in$.  

**Examples**:  
- $\text{Tom} \in \{\text{Tom}, \text{Jerry}\}$  
- $4 \in \mathbb{N}$  
- $1 \notin \{\{1\}\}$ (membership is not transitive!)  

**Symbols**:  
- $\notin$: "Not an element of"  
- $\ni$: Reverse membership (e.g., $\mathbb{N} \ni 4$).  

---

## Naive Set Theory  
**Definition**: Any "plausible" collection of elements is a set.  
- Elements can be **sets** or **urelements** (non-set primitives).  

**Examples**:  
- Explicit notation:  
  - $\emptyset = \{\}$ (empty set)  
  - $\{\text{Tom}, \text{Jerry}\}$  
  - $\mathbb{N} = \{0, 1, 2, \dots\}$  
  - $\{\emptyset, \{0\}, \{1\}, \{0,1\}, 7\}$  

⚠️ **Warning**: Unrestricted set comprehension leads to paradoxes (e.g., Russell’s Paradox: $\{S \mid S \notin S\}$).  

---

### Set Comprehension  
Define sets using rules (**set-builder notation**):  
- **Primes**: $\{x \in \mathbb{N} \mid x > 1 \land (\forall y,z \in \mathbb{N},\ yz = x \implies y=1 \lor z=1)\}$  
- **Even numbers**: $\{2x \mid x \in \mathbb{N}\}$  
- **Small naturals**: $\{x \in \mathbb{N} \mid x < 12\}$  

---

**Programming Analogy** (**List Comprehension**):  
set comprehension: ${ x | 0 ≤ x ≤ 100, x = 1 (mod 2) }$
**List Comprehension:**
```python  
# Python  
[x for x in range(101) if x % 2 == 1]  
```  
```haskell  
-- Haskell  
[x | x <- [0..100], x `mod` 2 == 1]  
```  

---

## Operations on Sets  

### Fundamental Operations  
- **Union**: $A \cup B = \{x \mid x \in A \lor x \in B\}$  
- **Intersection**: $A \cap B = \{x \mid x \in A \land x \in B\}$  
- **Difference**: $A \setminus B = \{x \mid x \in A \land x \notin B\}$  
- **Symmetric Difference**: $A \Delta B = \{x \mid x \in A \oplus x \in B\}$  

---

### Subsets & Supersets  
- **Subset**: $A \subseteq B$ iff $\forall x: x \in A \implies x \in B$  
- **Superset**: $A \supseteq B$ (equivalent to $B \subseteq A$)  
- **Proper Subset**: $A \subsetneq B$ means $A \subseteq B$ but $A \neq B$.  

⚠️ **Ambiguity Alert**:  
- "$A$ is **in** $B$" could mean $A \in B$ (membership) or $A \subseteq B$ (subset).  
- Example: $\{12\} \in \{\text{Moe}, \text{Larry}, \text{Curly}, \{12\}\}$ but $\{12\} \not\subseteq$ the same set.  

### Complement  
- **Complement**: $\overline{A} = \{x \mid x \notin A\}$ (requires a fixed **universe** $U$).  
- In practice, use $U \setminus A$ instead of $\overline{A}$ to avoid paradoxes.  

---

## Proving Things About Sets  

### Three Core Proof Strategies  
1. **Membership**: Show $x \in S$ using the definition of $S$.  
2. **Subset**: Show $S \subseteq T$ by proving $\forall x \in S: x \in T$.  
3. **Equality**: Show $S = T$ via $S \subseteq T$ **and** $T \subseteq S$.  

---

### Negative Proofs  
- **Non-Membership**: Find a counterexample for $x \in S$.  
- **Non-Subset**: Find $x \in S$ but $x \notin T$.  
- **Inequality**: Prove $S \nsubseteq T$ or $T \nsubseteq S$.  

---

## Example Lemma & Proof  

**Lemma**: For all sets $S, T$ and predicate $P$:  
1. $S \supseteq S \cap T$  
2. $S \subseteq S \cup T$  
3. $S \supseteq \{x \in S \mid P(x)\}$  
4. $S = (S \cap T) \cup (S \setminus T)$  

---

### Proof of Lemma  

#### 1. $S \supseteq S \cap T$  
- Let $x \in S \cap T$.  
- By definition, $x \in S$ **and** $x \in T$.  
- Thus, $x \in S$.  
- Since $x$ is arbitrary, $S \cap T \subseteq S$.  

---

#### 2. $S \subseteq S \cup T$  
- Let $x \in S$.  
- Then $x \in S \lor x \in T$ is true.  
- Hence, $x \in S \cup T$.  

---

#### 3. $S \supseteq \{x \in S \mid P(x)\}$  
- Let $x \in \{x \in S \mid P(x)\}$.  
- By definition, $x \in S$ (regardless of $P(x)$).  

---

#### 4. $S = (S \cap T) \cup (S \setminus T)$  
- **Step 1**: Show $S \subseteq (S \cap T) \cup (S \setminus T)$:  
  - For $x \in S$, either $x \in T$ (so $x \in S \cap T$) or $x \notin T$ (so $x \in S \setminus T$).  
- **Step 2**: Show $(S \cap T) \cup (S \setminus T) \subseteq S$:  
  - If $x \in (S \cap T)$ or $x \in (S \setminus T)$, then $x \in S$.  
- Equality follows from bidirectional inclusion.  

---

---

## Axiomatic Set Theory (ZFC)  

### Why ZFC?  
Naive set theory allows paradoxes (e.g., Russell’s Paradox). **Zermelo-Fraenkel (ZFC) axioms** restrict set construction to avoid contradictions.  

---

### Key Axioms of ZFC  
1. **Extensionality**:  
   - Sets with the same elements are equal:  
     $$\forall x, y: (x = y) \leftrightarrow (\forall z: z \in x \leftrightarrow z \in y)$$  

2. **Pairing**:  
   - For any sets $x, y$, the pair $\{x, y\}$ exists.  

3. **Union**:  
   - For any set of sets $S$, the union $\bigcup S$ exists.  

4. **Power Set**:  
   - For any set $S$, the power set $\mathcal{P}(S)$ (all subsets of $S$) exists.  

5. **Specification (Restricted Comprehension)**:  
   - For any set $S$ and predicate $P$, $\{x \in S \mid P(x)\}$ exists.  

6. **Infinity**:  
   - A set containing $\emptyset$ and closed under $x \mapsto x \cup \{x\}$ exists (encodes $\mathbb{N}$).  

7. **Choice**:  
   - For any set of nonempty sets, there exists a function selecting one element from each.  

---

## Cartesian Products & Relations  

### Ordered Pairs  
- **Definition**: $(a, b) = \{\{a\}, \{a, b\}\}$ (ensures order matters).  
- $\{a, b\} \neq (a, b)$ and $(a, b) \neq (b, a)$ unless $a = b$.  

---

### Cartesian Product  
- **Definition**:  
  $$A \times B = \{(x, y) \mid x \in A \land y \in B\}$$  
- **Example**:  
  - $\{1, 2\} \times \{3, 4\} = \{(1,3), (1,4), (2,3), (2,4)\}$  
  - $|A \times B| = |A| \cdot |B|$  

⚠️ **Non-commutative**: $A \times B \neq B \times A$ unless $A = B$.  

---

### Relations  
- A **relation** between $A$ and $B$ is any subset of $A \times B$.  
- **Example**:  
  - "$<$" on $\mathbb{N}$: $\{(1,2), (1,3), (2,3), \dots\}$  
  - Functions are a special type of relation (see below).  

---

## Functions  

### Definition  
A function $f: A \to B$ is a relation where:  
- **Every $x \in A$ maps to exactly one $y \in B$**.  
- **Notation**: $f(x) = y$ for $(x, y) \in f$.  

---

### Key Concepts  
- **Domain**: $A$ (input set).  
- **Codomain**: $B$ (output set).  
- **Image**: $\{f(x) \mid x \in A\}$ (actual outputs).  

---

### Function Examples  
1. **Linear Function**:  
   - $f: \mathbb{Z} \to \mathbb{Z},\ f(x) = x + 1$ (bijective).  
2. **Squaring Function**:  
   - $f: \mathbb{N} \to \mathbb{N},\ f(x) = x^2$ (injective but not surjective).  
3. **Floor Function**:  
   - $f: \mathbb{R} \to \mathbb{Z},\ f(x) = \lfloor x \rfloor$ (surjective but not injective).  

---

### Function Composition  
- For $f: A \to B$ and $g: B \to C$, define $g \circ f: A \to C$ as:  
  $$(g \circ f)(x) = g(f(x))$$  
- **Example**:  
  - $f(x) = x^2$, $g(x) = x + 1$ → $(g \circ f)(x) = x^2 + 1$.  

---

### Function Types  

![function types](./figures/functions.png)

| **Type**       | **Definition**                              | **Example**                     |  
|----------------|---------------------------------------------|---------------------------------|  
| **Injective**  | $f(x) = f(y) \implies x = y$                | $f(x) = 2x$ on $\mathbb{N}$     |  
| **Surjective** | $\forall y \in B, \exists x \in A: f(x)=y$ | $f(x) = x \mod 5$ on $\mathbb{Z}$ |  
| **Bijective**  | Both injective and surjective               | $f(x) = x + 1$ on $\mathbb{Z}$  |  

---

## Sequences & Cardinality  

### Sequences as Functions  
- A **sequence** $(a_1, a_2, \dots)$ is a function $a: \mathbb{N} \to A$.  
- **Tuples**: Finite sequences (e.g., $(a, b, c) \in A \times B \times C$).  

---

### Cardinality  
- **Definition**: $|A| = |B|$ iff there’s a bijection $A \leftrightarrow B$.  
- **Countable Sets**: $\mathbb{N}, \mathbb{Z}, \mathbb{Q}$ (same size as $\mathbb{N}$).  
- **Uncountable Sets**: $\mathbb{R}, \mathcal{P}(\mathbb{N})$ (strictly larger than $\mathbb{N}$).  

---

---

## Matrices  

### Definition  
A **matrix** is a rectangular array of numbers (or elements) arranged in **rows** and **columns**.  
- An $m \times n$ matrix has $m$ rows and $n$ columns.  
- **Square matrix**: $m = n$.  
- **Notation**:  
  $$A = \begin{bmatrix} a_{11} & a_{12} & \cdots & a_{1n} \\ a_{21} & a_{22} & \cdots & a_{2n} \\ \vdots & \vdots & \ddots & \vdots \\ a_{m1} & a_{m2} & \cdots & a_{mn} \end{bmatrix}$$  

---

### Matrix Operations  

#### 1. **Matrix Sum**  
- **Definition**: If $A$ and $B$ are $m \times n$ matrices, then $A + B$ is the $m \times n$ matrix with entries:  
  $$(A + B)_{ij} = A_{ij} + B_{ij}$$  
- **Example**:  
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} + \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 6 & 8 \\ 10 & 12 \end{bmatrix}$$  

#### 2. **Matrix Product**  
- **Definition**: If $A$ is $m \times k$ and $B$ is $k \times n$, then $AB$ is the $m \times n$ matrix where:  
  $$(AB)_{ij} = \sum_{r=1}^k A_{ir} B_{rj}$$  
- **Example**:  
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 1\cdot5 + 2\cdot7 & 1\cdot6 + 2\cdot8 \\ 3\cdot5 + 4\cdot7 & 3\cdot6 + 4\cdot8 \end{bmatrix} = \begin{bmatrix} 19 & 22 \\ 43 & 50 \end{bmatrix}$$  

⚠️ **Non-commutative**: $AB \neq BA$ in general.  

---

### Special Matrices  

#### 1. **Identity Matrix**  
- A square $n \times n$ matrix with $1$s on the diagonal and $0$s elsewhere:  
  $$I_n = \begin{bmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{bmatrix}$$  
- **Property**: For any $m \times n$ matrix $A$, $A I_n = A$ and $I_m A = A$.  

#### 2. **Zero Matrix**  
- A matrix where all entries are $0$.  

#### 3. **Transpose**  
- **Definition**: Flip rows and columns. If $A$ is $m \times n$, then $A^T$ is $n \times m$ with $(A^T)_{ij} = A_{ji}$.  
- **Example**:  
  $$\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}^T = \begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix}$$  

---

### Powers of Square Matrices  
- For a square matrix $A$, define $A^k = A \cdot A \cdot \ldots \cdot A$ ($k$ times).  
- **Example**:  
  $$A = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix} \implies A^2 = \begin{bmatrix} 1 & 2 \\ 0 & 1 \end{bmatrix}, \quad A^3 = \begin{bmatrix} 1 & 3 \\ 0 & 1 \end{bmatrix}$$  

---

## Zero-One Matrices  

### Definition  
Matrices where all entries are **0 or 1**. Used in Boolean algebra and graph theory.  

### Boolean Operations  
- **Join (OR)**: $A \lor B$ replaces addition.  
- **Meet (AND)**: $A \land B$ replaces multiplication.  

---

### Boolean Product  
- **Definition**: For $A$ ($m \times k$) and $B$ ($k \times n$), the Boolean product $A \odot B$ is:  
  $$(A \odot B)_{ij} = \bigvee_{r=1}^k (A_{ir} \land B_{rj})$$  
  - **AND** ($\land$) for multiplication, **OR** ($\lor$) for summation.  

**Example**:  
$$A = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}, \quad B = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}$$  
$$A \odot B = \begin{bmatrix} (1 \land 1) \lor (0 \land 0) & (1 \land 1) \lor (0 \land 1) \\ (0 \land 1) \lor (1 \land 0) & (0 \land 1) \lor (1 \land 1) \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}$$  

---

### Summary of Key Matrix Types  
| **Type**          | **Description**                          |  
|--------------------|------------------------------------------|  
| Square Matrix      | Equal rows and columns ($m = n$)         |  
| Identity Matrix    | Diagonal 1s, rest 0s ($A I = I A = A$)  |  
| Symmetric Matrix   | $A = A^T$                                |  
| Zero-One Matrix    | Entries are 0 or 1                       |  

---
