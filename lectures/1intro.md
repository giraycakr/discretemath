---
title: "discrete math-1intro"
author: "ammar daskin"
institute: "istanbul medeniyet university, computer engineering department"
urlcolor: red
linkstyle: bold
aspect-ratio: "16:9"
theme: black
center: false
align-items: left
align-content: left
justify-content: left
lang: tr
output: revealjs::revealjs_presentation
---

![logo](logo-tr.png)

# Course Content
This course teaches discrete mathematics that is used in Computer Science.
- The basic understanding of what mathematics is and how mathematical definitions and proofs work.
* The content and slides are mostly based on:
  * textbook: Discrete mathematics and its applications, Seventh Edition Kenneth H. Rosen.
  * Notes on Discrete Mathematics James Aspnes, [http://www.cs.yale.edu/homes/aspnes/classes/202/notes.pdf](http://www.cs.yale.edu/homes/aspnes/classes/202/notes.pdf)
  * And DeepSeek


---

## So why do I need to learn all this nasty mathematics?
- Computation is something that 
    - you can’t see and can’t touch, 
    - but it obeys strict, well-defined rules 
      - with astonishing accuracy over long periods of time.
- Computations are too big for you to comprehend all at once.

---

&rarr; So in order to understand computations, 
- we need a language that allows us to reason about things
  - we can’t see and can’t touch, 
  - that are too big for us to understand, but that nonetheless follow strict, simple, well-defined rules.

---

## But, isn’t math hard?  
- even apparently simple things like learning how to count or add require years of training  

---


🃏 [The Wason Selection Task](https://en.wikipedia.org/wiki/Wason_selection_task): Your Brain on Rules  
Which card(s) must you turn over in order to test that if a card shows an even number on one face, then its opposite face is blue?  

<div style="display: flex; gap: 20px; justify-content: center; background-color: green;">
  <div style="border: 2px solid black; width: 80px; 
  height: 120px; padding: 10px; text-align: center; background: red;">
    <span style="font-size: 32px;color:white;"> red </span>
  </div>
  <div style="border: 2px solid black; width: 80px; height: 120px; padding: 10px; text-align: center; background: blue;"\>
    <span style="font-size: 32px;color: white;"> blue </span>
  </div>
  <div style="border: 2px solid black; width: 80px; height: 120px; padding: 10px; text-align: center; background: white;"\>
    <span style="font-size: 64px;color:black;">4</span>
  </div>
  <div style="border: 2px solid black; width: 80px; height: 120px; padding: 10px; text-align: center; background: white;"\>
    <span style="font-size: 64px;color:black;">7</span>
  </div>
</div>  



- Abstract cards (e.g., numbers/letters) → Most get it wrong 😬
- Social rules (e.g., "voting in an election? Must be 18+!") → Most nail it 🎯

---

⚖️ Math vs. Legal Systems: Same DNA

| 1. Math Induction |  2. Royal Bloodline Rules|    
|-----------------|------------------------|  
If $x$ is in $S$, then $x + 1$ is in $S$. | If $x$ is of royal blood, then $x$’s child is of royal blood.  
*Builds infinite sets*| *Builds dynasties*   

- So why is statement (1) trickier to think about than statement (2)?
 - mathematical reasoning is very close to legal reasoning, which we do seem to be very good at.

---

## Content: Foundations and logic
Why: This is the assembly language of mathematics—the stuff at the bottom that everything else compiles to.

- Propositional logic.
- Predicate logic.
- Axioms, theories, and models.
- Proofs.
- Induction and recursion.

---

## Content: Basic mathematics on the real numbers
Why: You need to be able to understand, write, and prove equations and inequalities involving real numbers.
- Standard functions and their properties: addition, multiplication, exponentiation, logarithms.
- More specialized functions that come up in algorithm analysis: floor, ceiling, max, min.
- Techniques for proving inequalities, including:
  - General inequality axioms (transitivity, anti-symmetry, etc.)
  - Inequality axioms for R (i.e., how < interacts with addition,multiplication, etc.)
  - Techniques involving derivatives (not in this course)
- Special subsets of the real number: rationals, integers, natural numbers.

---

## Content: Fundamental mathematical objects 
Why: These are the mathematical equivalent of data structures, the way that more complex objects are represented
- set theory
- functions
- relations: equivalence relations, orders,etc.
- the basic number tower: 
  - countable universe $\mathbb{N}, \mathbb{Z}, \mathbb{Q}$
  - uncountable universe $\mathbb{R,C}$.

---

## Content: Modular Arithmetic
Why: Basis of modern cryptography.
- Arithmetic in $\mathbb{Z}_m$ .
- Primes and divisibility.
- Euclid’s algorithm and inverses.
- The Chinese Remainder Theorem.
- Fermat’s Little Theorem and Euler’s Theorem.
  - RSA encryption.

---

## Content: Linear Algebra* (only basics in this course)
Why: Shows up everywhere.
- Vectors and matrices.
- Matrix operations and matrix algebra.
- Inverse matrices and Gaussian elimination.
- Geometric interpretations.

---

## Content: Graphs
Why: Good for modeling interactions. Basic tool for algorithm design.
- Definitions: graphs, digraphs, multigraphs, etc.
- Paths, connected components, and strongly-connected components.
- Special kinds of graphs: paths, cycles, trees, cliques, bipartite graphs
- Subgraphs, induced subgraphs, minors.

---

## Content: Counting
Why: Basic tool for knowing what resources your program is going to
consume.
- Basic combinatorial counting: sums, products, exponents, differences, and quotients.
- Combinatorial functions: Factorials, Binomial coefficients.
- Advanced counting techniques: Inclusion-exclusion, Recurrences

---

## Content: Probability
Why: Can’t understand randomized algorithms or average-case analysis without it.  
Handy if you go to Vegas.
- Discrete probability spaces.
- Events.
- Independence.
- Random variables.
- Expectation and variance.
- Probabilistic inequalities

---

# How do we apply these to computers 🖥️ and AI 🧠?

---

**Logic & Proofs**  
- AI Reasoning: rule-based systems (e.g., expert systems, automated theorem provers).  
- Hardware Design: Digital circuits ("AND/OR/NOT" gates).  

**Set Theory/Relations** 
- Database design (SQL), 
- state machines, and language grammars.

**Graph Theory**  
- Neural Networks: Deep learning architectures are computational graphs.  
- Social Networks: Facebook friends = nodes/edges. 
  - Recommendation algorithms use graph traversals.  

---

<div style="display: flex; gap: 10px; justify-content: center;">
  <div style="border: 2px solid #333; padding: 10px;">Plaintext</div>
  <div style="font-size: 24px;">→ 🔑 →</div>
  <div style="border: 2px solid #333; padding: 10px; font-family: monospace;">
  RSA(C, d) = M</div>
</div>

**Modular Arithmetic** 
- Cryptography (RSA, blockchain)
- error-correcting codes (e.g., HTTPS, Bitcoin).

**Probability**  
- Randomized algorithms (e.g., quicksort) 
- Machine Learning: Bayesian networks, reinforcement learning, and statistical NLP all rely on probability axioms.  
- Error Handling: Checksums and probabilistic data structures (Bloom filters) use probability theory.  

---

**The Math Behind Tech 🔐⚡**
💡 **Key Insight:**
Computers are discrete mathematical objects. 
Their behavior is entirely governed by rules defined using logic, sets, functions, and combinatorics.

🔍 **The Wason Task Revisited:**
Humans struggle with abstract logical rules; but AI systems thrive on them. 
Discrete math gives machines their "rigor" advantage.

**Fun fact:** A single GPT-4 inference pass involves ~1 trillion matrix operations!

---

# Some Administrivia
- Attendance is not mandatory
- Weekly assignments via canvas
- Assignments are in group of 2,3, or max 4
- Some assignments will be peer graded
  - You will grade each others assignment anonymously. 
  - You will not see each others names
  - Group projects are graded intra group based.
- You can change your group before the assignment posted.

---

## Grading

30% assignments  
30% midterm  
40% final  

---

## Letter grades
- $> 90$ or $\approx$ top 10% AA
- $<35$ is FF.
- median $x$, and standard deviation $2s$ (we use half)
  - BA: $\approx[x+3s, x+4s)$ 
  - BB: $\approx[x+2s, x+3s]$ 
  - BC: $\approx[x+1s, x+2s)$ 
  - CC: $\approx[x-1s, x+1s)$ 
  - DC: $\approx[x-2s, x-1s)$ 
  - Depending on the value of $s$ and $x$, some slight changes may occur...  

---

# Mathematical Logic 🧠✨

We want to model reality in a way that fits in our heads.  
- **Ideal models** strip away irrelevant details and keep what matters.  

| **Reality** | → | **Model** | → | **Theory** |
|-------------|---|-----------|---|------------|
| Piles of rocks | → | $N = \{0, 1, 2, \dots\}$ | → | $\forall x : \exists y : y = x + 1$ |

---

## What if our model is **too big**? 🤔

**Solution:** Use **axioms** and **inference rules** to build a **theory**.  
- **Axioms:** True statements about the model.  
  - *Example:* "All fish are green."  
- **Inference Rules:** Tools to derive new truths.  
  - *Example:* From "All X are Y" and "Z is X," derive "Z is Y."  
- **Theory:** All statements built from axioms using inference rules.  

---

## Axioms, Models, and Inference Rules 🛠️

**Axioms:**  
- All fish are green.  
- George Washington is a fish.  

**Inference Rule:**  
- From "All X are Y" and "Z is X," derive "Z is Y."  

**Theory:**  
- George Washington is green! 🐟🎩  
  *(Our theory about George, fish, and greenness.)*  

---

### What is a **Model**? 🎯

A **model** is a collection of objects and their relationships.  
- **Theories** describe models.  
- A single theory can have **many models**:  
  - *Example:* A model with green fishy George Washington **and** 900-foot-tall Abraham Lincoln is consistent with the theory above.  
    *(The theory doesn’t mention Abraham Lincoln!)*  

---

### Consistency (Tutarlılık) ⚖️

A theory is **consistent** if it **cannot prove both P and not-P** for any P.  
- **What can go wrong?**  
  - Too many axioms → **Inconsistency**.  
    - *Example:*  
      - All fish are green.  
      - All sharks are not green.  
      - All sharks are fish.  
      - George Washington is a shark.  
      - **Contradiction!** 🚫  

---

### Underconstraining the Model (Modeli Yeterince Sınırlandırmamak) 🎈

If we don’t add enough axioms, the model becomes **underconstrained**.  
- *Example:* Peano axioms for natural numbers.  
  - Axiom: There is a number 0, and any number $x$ has a successor $S(x)$ (think $x + 1$).  
  - Underconstrained model: Only contains 0, where $S(0) = 0$.  

---

## The Language of Logic 🗣️

### Propositional Logic  
- **Basis of mathematical logic.**  
- **Propositions:** Statements that are either **true** or **false**.  
  - *Examples:*  
    - "George Washington is a fish."  
    - "2 + 2 = 5."  

---

### Predicate Logic 🚀  
- **Upgrade from propositional logic** to talk about **objects** and their **properties**.  
- Adds:  
  - **Constants:** Stand-ins for objects (e.g., "George Washington").  
  - **Predicates:** Stand-ins for properties (e.g., "is a fish").  

---

## Next week

More on logic..