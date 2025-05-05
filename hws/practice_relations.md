
**Practice Questions: Relations in Discrete Mathematics**  

---

### **Slide 1: Binary Relations & Cartesian Products**  
1. **Define**:  
   - What is a binary relation from set $A$ to set $B$?  
   - What is the Cartesian product $A \times B$?  

2. **Example**:  
   Let $A = \{x, y\}$ and $B = \{1, 2\}$.  
   - List all elements of $A \times B$.  
   - Define a relation $R$ from $A$ to $B$ where the first element is a vowel. Write $R$ as a set of ordered pairs.  

---

### **Slide 2: Matrix & Digraph Representations**  
1. **Matrix to Relation**:  
   Given $A = \{a, b\}$ and $B = \{1, 2, 3\}$, the matrix representation of relation $R$ is:  
   \[
   M_R = \begin{bmatrix}
   1 & 0 & 1 \\
   0 & 1 & 0
   \end{bmatrix}
   \]  
   List all ordered pairs in $R$.  

2. **Digraph Analysis**:  
   Draw the digraph for the relation $R = \{(1,1), (1,2), (2,3), (3,2)\}$ on $A = \{1, 2, 3\}$. Is this relation reflexive? Symmetric? Transitive?  

---

### **Slide 3: Properties of Relations**  
1. **Classification**:  
   For the relation $R = \{(a, b) \mid a + b \text{ is even}\}$ on $\mathbb{Z}$, determine if $R$ is:  
   - Reflexive  
   - Symmetric  
   - Antisymmetric  
   - Transitive  

2. **Counterexample**:  
   Give an example of a relation on $\{1, 2, 3\}$ that is symmetric and transitive but not reflexive.  

---

### **Slide 4: Equivalence Relations & Partitions**  
1. **Equivalence Classes**:  
   Let $R$ be the relation on $\mathbb{Z}$ defined by $aRb$ iff $a \equiv b \pmod{4}$.  
   - Prove $R$ is an equivalence relation.  
   - List all equivalence classes of $R$.  

2. **Partition to Relation**:  
   Given the partition $\{\{1, 3\}, \{2, 4\}\}$ of $A = \{1, 2, 3, 4\}$, describe the corresponding equivalence relation.  

---

### **Slide 5: Partial Orders & Hasse Diagrams**  
1. **Poset Analysis**:  
   Let $R$ be the "divides" relation ($\mid$) on $A = \{2, 4, 6, 8\}$.  
   - Verify $R$ is a partial order.  
   - Draw the Hasse diagram for $(A, R)$.  
   - Identify minimal and maximal elements.  

2. **Topological Sort**:  
   Apply the topological sorting algorithm to the poset represented by the following Hasse diagram:  
   ```mermaid  
   graph BT  
       d --> b  
       d --> c  
       b --> a  
       c --> a  
   ```  

---

### **Slide 6: Lattices & Applications**  
1. **Lattice Check**:  
   Is the poset $(\{1, 2, 3, 4, 6\}, \mid)$ a lattice? Justify your answer.  

2. **Real-World Example**:  
   In the military security model, suppose $(A_1, C_1) = (\text{Secret}, \{\text{Navy}\})$ and $(A_2, C_2) = (\text{TopSecret}, \{\text{Navy, AirForce}\})$.  
   - Can information flow from $(A_1, C_1)$ to $(A_2, C_2)$?  
   - What is the least upper bound of these two security classes?  

--- 

**End of Practice Questions**  


# Answers to Practice Questions from Deepseek-R1

*Below is answers from DeepSekk-R1: Check your answers using definitions, theorems, and examples from the lecture notes!*

---

### **Slide 1: Binary Relations & Cartesian Products**  
1. **Define**:  
   - A **binary relation** from set $A$ to $B$ is a subset of $A \times B$.  
   - The **Cartesian product** $A \times B$ is the set of all ordered pairs \((a, b)\) where $a \in A$ and $b \in B$.  

2. **Example**:  
   - $A \times B = \{(x, 1), (x, 2), (y, 1), (y, 2)\}$.  
   - Assuming $y$ is treated as a vowel: $R = \{(y, 1), (y, 2)\}$.  

---

### **Slide 2: Matrix & Digraph Representations**  
1. **Matrix to Relation**:  
   - $R = \{(a, 1), (a, 3), (b, 2)\}$.  

2. **Digraph Analysis**:  
   - **Reflexive**: No (missing loops for 2 and 3).  
   - **Symmetric**: No (e.g., $1 \to 2$ exists, but $2 \to 1$ does not).  
   - **Transitive**: No (e.g., $1 \to 2 \to 3$ exists, but $1 \to 3$ does not).  

---

### **Slide 3: Properties of Relations**  
1. **Classification**:  
   - **Reflexive**: Yes.  
   - **Symmetric**: Yes.  
   - **Antisymmetric**: No.  
   - **Transitive**: Yes.  

2. **Counterexample**:  
   - $R = \emptyset$ on $\{1, 2, 3\}$.  

---

### **Slide 4: Equivalence Relations & Partitions**  
1. **Equivalence Classes**:  
   - $R$ is an equivalence relation.  
   - Classes: \([0], [1], [2], [3]\) (e.g., \([0] = \{..., -4, 0, 4, 8, ...\}\)).  

2. **Partition to Relation**:  
   - $R = \{(1,1), (1,3), (3,1), (3,3), (2,2), (2,4), (4,2), (4,4)\}$.  

---

### **Slide 5: Partial Orders & Hasse Diagrams**  
1. **Poset Analysis**:  
   - **Partial Order**: Yes (reflexive, antisymmetric, transitive).  
   - **Hasse Diagram**:  
     ```mermaid  
     graph BT  
         8 --> 4  
         4 --> 2  
         6 --> 2  
     ```  
   - **Minimal Element**: $2$. **Maximal Elements**: $6, 8$.  

2. **Topological Sort**:  
   - Possible orderings: $[d, b, c, a]$ or $[d, c, b, a]$.  

---

### **Slide 6: Lattices & Applications**  
1. **Lattice Check**:  
   - No. For $2$ and $3$, $\gcd(2,3) = 1 \notin \text{set}$.  

2. **Real-World Example**:  
   - **Information Flow**: Yes (Secret ≤ TopSecret and \(\{Navy\} \subseteq \{Navy, AirForce\}\)).  
   - **Least Upper Bound**: \((TopSecret, \{Navy, AirForce\})\).  

--- 

**Verified with Lecture Notes** ✅