---
title: "Discrete Mathematics - math logic"
author: "Ammar Daskin"
institute: "Istanbul Medeniyet University, Computer Engineering Department"
theme: black

---

<style type="text/css">
div {
  font-size: clamp(11px, 3vw, 28px);
}
</style>

![logo](logo-tr.png)

# Mathematical Logic 🧠✨  
*"The art of reasoning about reasoning."*

- The content is mostly based on  [Notes  by James Aspnes](http://www.cs.yale.edu/homes/aspnes/classes/202/notes.pdf)
* Slides are prepared with DeepSeek-R1  

---

## Basics 🌱

### **Modeling Reality**  
- **Goal:** Simplify complex reality into manageable mental models.  
- **Ideal Models:** Strip away noise, keep essentials.  

| **Reality**      | → | **Model**               | → | **Theory**                          |  
|-------------------|---|-------------------------|---|-------------------------------------|  
| Piles of rocks 🪨 | → | `N = {0, 1, 2, ...}`    | → | `∀x ∃y : y = x + 1` (Successor axiom) |  

---

## Axioms & Inference Rules ⚙️  
**Problem:** Models can be *too big*.  
**Solution:** Build theories with axioms and rules.  

### Key Components 🔑  
| Component          | Description                          | Example 💡 |  
|--------------------|--------------------------------------|-----------|  
| **Axioms**         | Foundational truths.                | "All fish are green." 🐟 |  
| **Inference Rules** | Tools to derive new truths.          | Modus Ponens: `p → q, p ⊢ q` |  
| **Theory**         | All statements built from axioms.    | "George Washington is green!" 🎩 |  

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

## Propositional Logic 📜  
*The simplest logic: True/False statements.*  

### Propositions ✅❌  
- **Definition:** Declarative sentences with a truth value.  
  - *Examples:*  
    - "2 + 2 = 4" ✔️  
    - "Toronto is Canada’s capital" ❌  

---

### Non-Propositions 🚫  

- Questions, commands, or statements with variables:  
  - "What’s 1 + 1?" ❓  
  - Read this carefully!
  - "`x + 1 = 2`" 📊 *(Depends on `x`!)*  


---

### Operations on Propositions

We use placeholder names like $p, q, r$ for propositions.

---


## Logical Operations 🔄  

| Operator       | Symbol | Meaning                          | Example 💬 |  
|----------------|--------|----------------------------------|-----------|  
| **Negation**   | `¬p`   | "Not p"                          | `¬(Sun is hot) = "Sun is not hot"` 🌑 |  
| **AND**        | `p ∧ q`| Both true                        | "Rain ∧ Umbrella = Stay dry" ☔ |  
| **OR**         | `p ∨ q`| At least one true                | "Coffee ∨ Tea = Morning bliss" ☕ |  
| **Implication**| `p → q`| If p, then q                     | "Study → Pass" 📚→🎓 |  
| **Biconditional**| `p ↔ q`| "p if and only if q"          | "2+2=5 ↔ I’m a penguin" 🐧 |  

---

**Exclusive OR:**  $p\oplus q$  
- true when only one of $p$ or $q$ is true.
- not used much in classical logic 
- important for many computing applications:
  - It corresponds to addition modulo 2.
  - It has nice reversibility properties 
    - e.g., $p \oplus (p \oplus q)$ always has the same truth-value as $q$.

---

**More on AND:** $p \land q$ is true only when both $p$ and $q$ are true.
  - Example: "I like to eat ice cream and I own a private Caribbean island."
  - Translating from English: Sometimes "but" can also be used as "and":
    - "2 + 2 = 4 **but** 3 + 3 = 6" 
      - translates to $(2 + 2 = 4) \land (3 + 3 = 6)$.  

---


**Implication:** represents an `"if...then"` claim.
  - If $p$ implies $q$, then we write $p \rightarrow q$ or $p \implies q$.
  - In English: "If $p$, then $q$" 
    - as in "If you step on your own head, it will hurt."
  - $p \rightarrow q$ 
    - **true** when both $p$ and $q$ are **true**.
  - $p \rightarrow q \equiv \neg p \lor q$:
    - When $p$ is **false**, $p \rightarrow q$ is **true** (no matter what truth value $q$ has).

---

**Biconditional:** Suppose that $p \implies q$ and $q \implies p$, 
  - either **both** $p$ and $q$ are **true** or **both** $p$ and $q$ are **false**.
  - In this case, 
    $$p \iff q \text{ or }  p \leftrightarrow q$$

  - Example: "2 + 2 = 5 **if and only if** I am here!"

---

### Precedence

**Compound proposition**: The result of any of these operations.

| Operator | Notation | Precedence |
|----------|----------|------------|
| NOT      | $\neg p$, $\overline{p}$, $\sim{p}$ | Highest |
| AND      | $p \land q$ | |
| XOR      | $p \oplus q$ | |
| OR       | $p \lor q$ | |
| Implies  | $p \implies q$, $p \rightarrow q$, $p \supset q$ | |
| IFF      | $p \iff q$, $p \leftrightarrow q$ | Lowest |

---

### Examples

  $$(\neg p \lor q \land r \rightarrow s \leftrightarrow t)$$ 
-  $$(\neg p \lor q \land r \rightarrow s \leftrightarrow t) 
 \equiv ((((\neg p) \lor (q \land r)) \leftarrow s) \leftrightarrow t)$$ <!-- .element: class="fragment" -->

---


$\lor$ and $\land$ are associative:  
- $(p \lor q \lor r) \equiv ((p \lor q) \lor r) \equiv (p \lor (q \lor r))$ 
 - $(p \land q \land r) \equiv ((p \land q) \land r) \equiv (p \land (q \land r))$ 
  

**This convention is not universal.** Many mathematicians give $\lor$ and $\land$ the same precedence: $p \land q \lor r$ is ambiguous.

---


**Implication** is not associative. The convention is that it binds to the right:
   - $a \rightarrow b \rightarrow c \equiv a \rightarrow (b \rightarrow c)$
   - $a \leftrightarrow b \leftrightarrow c \equiv ?$ **No idea without parentheses!**

---


# Truth Tables 🎰  

- **T** for true, **F** for false
- Computer scientists use **1** for true, **0** for false
- Any combination of values for inputs gives a truth table.

---

### Truth Table for Negation  
| `p` | `¬p` |  
|-----|-----|  
| 0   | 1   |  
| 1   | 0   |  




| `p` | `¬p` |  
|-----|-----|  
| F   | T   |  
| T   | F   |  

---


### Implication (`p → q`)  
| `p` | `q` | `p → q` |  
|-----|-----|---------|  
| T   | T   | T       |  
| T   | F   | F       |  
| F   | T   | T       |  
| F   | F   | T       |  

*(Fun fact: "False implies anything" is always true! 🤯)*  

---

### Truth Table for Logical Operations

| $p$ | $q$ | $p \lor q$ | $p \oplus q$ | $p \land q$ | $p \implies q$ | $p \iff q$ |
|---------|---------|----------------|------------------|-----------------|--------------------|----------------|
| `0`       | `0`       | 0              | 0                | 0               | 1                  | 1              |
| `0`       | `1`       | 1              | 1                | 0               | 1                  | 0              |
| `1`       | `0`       | 1              | 1                | 0               | 0                  | 0              |
| `1`       | `1`       | 1              | 0                | 1               | 1                  | 1              |

**Proving a proposition using a truth table is a simple version of model checking:** 
  - enumerate all possible models of  given propositions and see if it holds in all models.

---

# Tautologies and Logical Equivalence

---

**A tautology:** A compound proposition that is always true no matter what the truth-values of the propositional variables.

- $p \rightarrow p$
- $p \lor \neg p$
- $\neg(p \land \neg p)$

---

**A contradiction:** A compound proposition that is always false.

- The negation of a tautology is a contradiction (and vice versa).

---

**Logical equivalence:** The tautology of the form $X \iff Y$.

- $X$ and $Y$ are compound propositions.
- $X$ and $Y$ are logically equivalent.
- $X  \equiv Y $
- "$\equiv $" does the same thing for Boolean formulas that "$=$" does for algebraic formulas.

---

### Proving Logical Equivalence

1. Either construct a truth table to show $X  \iff Y$ is a tautology.
2. Or transform $X$ and $Y$ into known logical equivalences.

---

### Examples of Logical Equivalence

1. $p \land \neg p \equiv 0$
2. $p \lor p \equiv p$
3. $p \implies q \equiv \neg p \lor q$

---

4. De Morgan's laws:
   - $\neg(p \lor q) \equiv \neg p \land \neg q$
   - $\neg(p \land q) \equiv \neg p \lor \neg q$
5. Distributive laws:
   - $p \lor (q \land r) \equiv (p \lor q) \land (p \lor r)$
   - $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$
6. $(p \implies r) \lor (q \implies r) \equiv (p \land q) \implies r$

---

### Common Logical Equivalences

| Equivalence | Description |
|-------------|-------------|
| $$\neg \neg p \equiv p $$ | Double negation |
| $$\neg(p \land q) \equiv \neg p \lor \neg q$$ | De Morgan's law |
| $$\neg(p \lor q) \equiv \neg p \land \neg q$$ | De Morgan's law |

---

|  |  |
|-------------|-------------|
| $$p \land q \equiv q \land p$$ | Commutativity of AND |
| $$p \lor q \equiv q \lor p$$ | Commutativity of OR |
| $$p \land (q \land r) \equiv (p \land q) \land r$$ | Associativity of AND |
| $$p \lor (q \lor r) \equiv (p \lor q) \lor r$$ | Associativity of OR |


---

|  |  |
|-------------|-------------|
| $$p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$$ | AND distributes over OR |
| $$p \lor (q \land r) \equiv (p \lor q) \land (p \lor r)$$ | OR distributes over AND |
| $$p \implies q \equiv \neg p \lor q$$ | Equivalence of implication and OR |

---


|  |  |
|-------------|-------------|
| $$p \implies q \equiv \neg q \implies \neg p$$ | Contraposition |
| $$p \iff q \equiv (p \implies q) \land (q \implies p)$$ | Expansion of IFF |
| $$p \iff q \equiv \neg p \iff \neg q$$ | Inverse of IFF |
| $$p \iff q \equiv q \iff p$$ | Commutativity of IFF |

---

### Proof by Contraposition

The contrapositive of $p \rightarrow q$ is $\neg q \rightarrow \neg p$.

- $p \rightarrow q$: 
  - `"If I am a human, then I am a mammal."`
- $\neg q \rightarrow \neg p$: 
  - `"If I am not a mammal, then I am not a human."`

**Note:** Indirect proof assumes $\neg p$ and derives a contradiction.

---

### Inverse

The inverse of $p \rightarrow q$ is $\neg p \rightarrow \neg q$.

- $p \rightarrow q$: 
  - `"If I am a human, then I am a mammal."`
- $\neg p \rightarrow \neg q$: 
  - `"If I am not a human, then I am not a mammal."`
- The truth values are different.

---

### Converse

The converse of $p \rightarrow q$ is $q \rightarrow p$.

- $p \rightarrow q$: 
  - `"If I am a human, then I am a mammal."`
- $q \rightarrow p$: 
  - `"If I am a mammal, then I am a human."`
- The truth values are different.

---

### Equivalences Involving True and False

**Any tautology** is equivalent to **true**; 
**any contradiction** is equivalent to **false**.

---

**The law of excluded middle.**

- $P \lor \neg P \equiv 1$: 
  - "Either Socrates is mortal, or it is not the case that Socrates is mortal."

We can do case analysis where we prove that some proposition $Q$ holds by showing first $P \rightarrow Q$ and then that also $\neg P \rightarrow Q$.
  
---

**The law of non-contradiction.** 
- $P \land \neg P \equiv 0$: 
  - Nothing can both be and not be.

---

### Absorption Laws

|    Equivalences   |------------| Equivalences  |
|-------------| :-----: |-------------|
| $P \land 0 \equiv 0$ ||  $P \oplus 0 \equiv P$ |
| $P \lor 0 \equiv P$ || $P \oplus 1 \equiv \neg P$ | |
| $P \land 1 \equiv P$ || $P \rightarrow 0 \equiv \neg P$ | |
| $P \lor 1 \equiv 1$ || $P \rightarrow 1 \equiv 1$ | |
| $P \iff 0 \equiv \neg P$ || $0 \rightarrow P \equiv 1$ | |
| $P \iff 1 \equiv P$ || $1 \rightarrow P \equiv P$ | |


**Example:** Compute $(P \land (P \rightarrow Q)) \rightarrow Q \equiv ?$

---

# Normal Forms

---

## Normal Forms & Resolution 🧩  

### Conjunctive Normal Form (CNF)  
- **Structure:** AND of OR clauses.  
  - *Example:*  
    `(A ∨ B) ∧ (¬C ∨ D)`  

### Resolution Rule 💡  
- Combine clauses to deduce new truths:  
  - From `(A ∨ B)` and `(¬A ∨ C)`, derive `(B ∨ C)`.  

---

### Conjunctive Normal Form (CNF)

**Conjunctive normal form (CNF):** A compound proposition ANDs of ORs of one or more variables.

- $P$
- $(P \lor Q) \land R$
- $(P \lor Q) \land (P \lor \neg R) \land (\neg P \lor Q \lor S \lor T \lor \neg U)$

---

### Converting to CNF

Using  
- $P \rightarrow Q \equiv \neg P \lor Q$, 
- De Morgan's laws, 
- and the distributive law, 
it is possible to rewrite any compound proposition in CNF.

**Examples:**

1. $(P \lor Q) \land (P \lor \neg R) \land (\neg P \land Q)$
2. $(P \lor (Q \land R)) \land (P \lor \neg R) \land (\neg P \lor Q)$

---

## Simplifying CNF

This does not produce the simplest CNF.

---

### Fun Example: The Head-Cutter’s Dilemma ⚔️  
*"If you draw your sword, I cut your head. If you don’t, I cut your head."*  

---

- **CNF:** `(¬Draw ∨ Cut) ∧ (Draw ∨ Cut)`  
- **Simplifies to:** `Cut` *(You’re doomed either way! 💀)*  

---


## Simplifying CNF: The Head-Cutter’s Paradox ⚔️  
*"Draw your sword or not, your head rolls!"*  

### Simplification Steps 🔍   $$(P \rightarrow Q) \land (\neg P \rightarrow Q)$$
1. Start with implications:  

--- 

   $$(P \rightarrow Q) \land (\neg P \rightarrow Q) \equiv (\neg P \lor Q) \land (P \lor Q)$$  
2. Distribute and simplify:  

---

  $$(\neg P \land P) \lor (\neg P \land Q) \lor (Q \land P) \lor Q \equiv 0 \lor (\text{...}) \lor Q \equiv Q$$  

3. **Conclusion:**  
  $$Q \, \text{(I will cut off your head! 💀)}$$  

---

## Resolution in CNF 🔄  
*A rule of inference for deducing truths.*  

### How It Works 🛠️  
1. **Premises:** CNF clauses.  
2. **Look for:** A literal and its negation 
   1. e.g., $\textbf{Snow}$  and $\neg \textbf{Snow} $.  
3. **Resolve:** Remove conflicting literals, merge clauses.  

---

**Example:**  
| Premise 1: $Rain \lor \textbf{Snow}$ ☔️❄️ |  
| Premise 2: $\neg \textbf{Snow} \lor Traffic$ 🚗  |  
| **Resolve to:** $Rain \lor Traffic$ ☔️🚗  |  

---

## Resolution Proof Walkthrough 🧩  

### Starting Clauses:  
$$(P \lor Q) \land (P \lor \neg R) \land (\neg P \lor Q) \land (\neg Q \lor R)$$  

Inside CNF, look for a simple proposition and its negation and resolve them into a conclusion.

---

### Step-by-Step Resolution 🔄  
1. **Add $Q$:** (From $(P \lor Q) \land (\neg P \lor Q)$ )  
   $$\vdash (P \lor Q) \land (P \lor \neg R) \land (\neg P \lor Q) \land (\neg Q \lor R) \land \mathbf{Q}$$  
2. **Resolve $\neg Q \lor R$ with $Q $:**  
   $$\vdash R \quad \text{(∴ Add $R$)}$$  
3. **Resolve $P \lor \neg R$ with $R $:**  
   $$\vdash P \quad \text{(Boom! 💥)}$$  

**Final Conclusion:** $P$ 

---


### Simplifying CNF (Continued)

$$(P \rightarrow Q) \land (\neg P \rightarrow Q)$$

---

Simplifying $(P \rightarrow Q) \land (\neg P \rightarrow Q)$:

$$\equiv    (\neg P \lor Q) \land (P \lor Q)$$

$$\equiv (\neg P \land P) \lor (\neg P \land Q) \lor (Q \land P) \lor (Q \land Q)$$

$$\equiv 0 \lor (\neg P \land Q) \lor (Q \land P) \lor Q$$

$$\equiv (\neg P \land Q) \lor (Q \land P) \lor Q$$

The proposition is in **disjunctive normal form**.

- If either of the other clauses are true, so is $Q$.
- What the master just said was **"I will cut off your head."**

---

## Predicate Logic 🚀  
*Level up with variables and quantifiers!*  

---

Using only **propositional logic**, we can express:

1. Socrates is a man.   **(axiom)**
2. If Socrates is a man, then Socrates is mortal.   **(axiom)**
3. Therefore, Socrates is mortal. **(conclusion)**

The inference rule **modus ponens**: From $p$ and $p \implies q$, you can deduce $q$.

---

### Propositional Logic Limitation  
1. Socrates is a man. 👨  
2. Socrates is mortal. 💀  

    *But what about Spocrates🧙*,
      - Socrates’s infinitely more logical cousin  

---

### We would like to argue that

1. Spocrates is a man.🧙
2. If Spocrates is a man, then Spocrates is mortal.💀
   - **Unfortunately, this step depends on knowing that humanity implies mortality for everybody, not just Socrates.** 
  
3. Therefore, Spocrates is mortal.

**What we would like is a general way to say that humanity implies mortality for everybody.**

---

### Variables and Predicates

let $x, y, z$, etc. stand for any element of our universe of discourse or domain.  

**Predicates:** Statements whose truth value depends on the value of the objects.

- “$x$ is human.”
- “$x$ is the parent of $y$.”
- “$x + 2 = x^2$.”

---

### Predicates = Properties/Relations 

Predicates are abbreviated by capital letters and a list of arguments (like $F(x)$):

| Predicate | Meaning | Example 💡 |  
|-----------|---------|-----------|  
| $H(x)$ | $x$ is human | $H(\text{Socrates}) = \text{👨}$ |  
| $P(x, y)$ | $x$ is $y$’s parent | $P(\text{Mom}, \text{Me}) = \text{👩👧}$ |  
| $Q(x)$ | $x + 2 = x^2$ | $Q(2) = \text{✅}, Q(0) = \text{❌}$ |  


---

## Quantifiers: ∀ and ∃ 🌟  

### Universal Quantifier (`∀`) 🌍  
- "For all x, P(x) holds."  
- **Example:**  
    `∀x: (Human(x) → Mortal(x))`  
    *(All humans are mortal.)*  

---

### Universal Quantifier ($\forall$) 🌍  
- **Meaning:** "For all..."  
- **Example:** You can also use set-membership notation 
  $$\forall x \in Z: (x > 0 \rightarrow x + 1 > 0)$$ 
  - All positives stay positive ➕
  - Or $\forall x: x \in Z \land (x > 0 \rightarrow x + 1 > 0)$ 

 
---

### Existential Quantifier (`∃`) 🔍  
- "There exists an x where P(x) holds."  
- **Example:** 
    `∃x (Unicorn(x) ∧ Sparkly(x))`  
    *(Sparkly unicorns exist! 🦄✨)*  

---



### Existential Quantifier ($\exists$) 🔍  
- **Meaning:** "There exists..."  
- **Example:**  
  $$\exists x \in Z: (x^2 = 81)$$  
  - (Someone squared is 81! 9️⃣)

---

### Existential Quantifier ($\exists$) 🔍  
- $\exists x \in Z: (x = x^2)$ 
  - $\exists x: x \in Z \land (x = x^2)$
-  $\exists x: P(x)$ is equvailent to a very large OR
  - $\exists x \in N: P(x)$ is equivalent to 
  $P(0) \lor P(1)\lor ...$

---



### Negation of Quantifiers

- $\neg \forall x : P(x) \equiv \exists x : \neg P(x)$:
  - If you want to show that not all humans are mortal, it’s equivalent to finding some human that is not mortal.
  
- $\neg \exists x : P(x) \equiv \forall x : \neg P(x)$:
  - To show that no human is mortal, you have to show that all humans are not mortal.

---

### Negating Quantifiers 🚫  
| Quantifier | Negation | Example 🔄 |  
|------------|----------|------------|  
| $\forall x P(x)$ | $\exists x \neg P(x)$ | "Not all birds fly" ≡ "Some bird doesn’t fly 🐦✖️" |  
| $\exists x P(x)$ | $\forall x \neg P(x)$ | "No unicorns exist" ≡ "All things are ¬unicorns 🦄❌" |  

---

### Restricting the Scope of a Quantifier

- By set-membership.
- By implication.
- By restriction in the qualifier.

**Example 1:**
- $\forall x : x > 0 \implies x - 1 \geq 0$
- $\forall x > 0 : x - 1 \geq 0 $

**Example 2:**
- $\exists x : x > 0 \land x^2 = 81$
- $\exists x > 0 : x^2 = 81$

---


### Nested Quantifiers 🔄  
 **"No Largest Prime"** 🔢  
$$\forall x \exists y: (y > x \land \text{Prime}(y))$$  
- “For any $x$, there is a bigger $y$ that is prime.”  (Primes go forever! ♾️)

**Exercise:** “There does not exist an $x$ that is prime and any $y$ greater than $x$ is not prime.”

---

### "No Largest Prime" 🔢  

$$\neg \exists x : (\text{Prime}(x) \land \forall y : y > x \implies \neg \text{Prime}(y))$$

---

### Popularity Contest  
$$\forall x \exists y \, \text{likes}(x, y)$$
-  *Everyone likes someone.*  

$$\exists y \forall x \, \text{likes}(x, y)$$
- *Someone is universally liked! 🌟*  

---

#

## Normal Forms & Resolution 🧩  

### Conjunctive Normal Form (CNF)  
- **Structure:** AND of OR clauses.  
  - *Example:*  
    `(A ∨ B) ∧ (¬C ∨ D)`  

### Resolution Rule 💡  
- Combine clauses to deduce new truths:  
  - From `(A ∨ B)` and `(¬A ∨ C)`, derive `(B ∨ C)`.  

---

## Negation ✨  
1. **De Morgan’s Laws:**  
   - `¬(A ∧ B) ≡ ¬A ∨ ¬B`  
   - `¬(A ∨ B) ≡ ¬A ∧ ¬B`  
2. **Contrapositive:** `p → q ≡ ¬q → ¬p`  
3. **Quantifier Negation:**  
   - `¬∀x P(x) ≡ ∃x ¬P(x)`  
   - `¬∃x P(x) ≡ ∀x ¬P(x)`  

---


## From Socrates to Spocrates 🧙♂️  
**Propositional Logic Limitation:**  
1. Socrates is a man. 👨  
2. Socrates is mortal. 💀  
   *But what about Spocrates?*  

**Predicate Logic Fix:**  
$$\forall x \, (\text{Human}(x) \rightarrow \text{Mortal}(x)) \quad \text{(All humans are mortal!)}$$  

---

## Variables & Predicates 🔤  
### Predicates = Properties/Relations  
| Predicate | Meaning | Example 💡 |  
|-----------|---------|-----------|  
| $H(x)$ | $x$ is human | $H(\text{Socrates}) = \text{👨}$ |  
| $P(x, y)$ | $x$ is $y$’s parent | $P(\text{Mom}, \text{Me}) = \text{👩👧}$ |  
| $Q(x)$ | $x + 2 = x^2$ | $Q(2) = \text{✅}, Q(0) = \text{❌}$ |  

---



## Functions 

A function symbol looks like a predicate but returns an object and does not compute the truth value.

- $2 + 2 = 5 $:
  - Three constants: 2, 2, and 5.
  - A two-argument function: $+$.
  - A predicate: $=$.

---

### Functions 

Functions let us populate our universe without including a lot of axioms.  

- **Example:** $S(x) = \text{successor of } x$  (the next number)
we can count in $N$ 🔢  as:
$$0, S(0), S(S(0)), S(S(S(0)))...$$  

---

### ⚖️ Equality ($ = $) 

The equality predicate $=$, included as a standard part of predicate logic.

- $x = y$:
  - $x$ and $y$ are the same elements of the domain.

---

### Equality Axioms 🔗  

- **Reflexivity (yansima):** $\forall x : x = x$
- **Substitution(yerine koyma):** $\forall x \forall y : x = y \implies (P(x) \leftrightarrow P(y))$
  - Substitution rule: $x = y, P(x) \vdash P(y)$
- **Symmetry:** $\forall x \forall y : x = y \implies y = x$
- **Transitivity(geciskenlik):** $\forall x \forall y \forall z : x = y \land y = z \implies x = z$

---

## Uniqueness ($ \exists! $) 🦄  
*"There’s exactly one..."*  

$$\exists!x P(x)$$
There exists a **unique** $x$ such that $P(x)$.

---

### Uniquenes
$$\exists!x P(x) \equiv \exists x \left(P(x) \land \forall y \, (P(y) \rightarrow y = x)\right)$$  
“There is an $x$ for which $P(x)$ is true, and any $y$ for which $P(y)$ is true is equal to $x$.”

**Example:**  
$$\exists!x : (x + 1 = 12) \quad \text{(Only $x = 11$ works! 1️⃣1️⃣)}$$  
- To expand $\exists!x P(x)$, apply $P(y) \implies x = y$  
---

### More on Expanding ($ \exists! $)

$$\exists!x P(x) \equiv \exists x \left(P(x) \land (\forall y : x \neq y \implies \neg P(y))\right)$$

“Any $y$ that is not $x$ doesn’t satisfy $P$.”

You can also apply De Morgan’s laws to this:

$$\exists!x P(x) \equiv \exists x \left(P(x) \land (\neg \exists y : x \neq y \land P(y))\right)$$

“There is an $x$ with $P(x)$, but there is no $y \neq x$ with $P(y)$.”

---


## Models in Predicate Logic 🏛️  
**remember:** a  theory is a set of statements

**Models in propositional logic:**, we can build truth tables that describe all possible settings of the truth-values of the literals.

**Models in Predicate Logic:** We use **structures**    
- **Structure:** Objects + relationships + functions.  
- **Purpose:** Prove consistency or independence of theories.  

---

### Structures

- A set of objects or elements (set theory).
- Description of which elements fill in for the constant symbols.
- Which predicates hold for which elements.
- What the value of each function symbol is when applied to a list of arguments.
  - **Signature:** What constant, predicate, and function symbols are available.

A structure is a **model** of a particular theory if each statement in the theory is true in the model.

---

### Examples 🌟  
| Axiom | Model |  
|-------|-------|  
|$\neg \exists x$ | Only empty set ⚫ |  
| $\exists!x$ | Only single-element set 1️⃣ |  
| Family tree axioms(?) | Royal family tree 👑🌳 |  

---

- The family tree of the kings of France is a model of the theory containing the two axioms:
  - $\forall x \forall y \forall z : \text{Parent}(x, y) \land \text{Parent}(y, z) \implies \text{GrandParent}(x, z)$
  - $\forall x \forall y : \text{Parent}(x, y) \implies \neg \text{Parent}(y, x)$

This still allows for the possibility that there are some $x$ and $y$ for which $\text{Parent}(x, y)$ and $\text{GrandParent}(y, x)$ are both true.

---

###  Use of Models for Theory 🏛️  

### Consistency and Completeness of a Theorem  
| Concept         | Description                          |  
|-----------------|--------------------------------------|  
| **Consistency** | No contradictions (`P ∧ ¬P`).        |  
| **Completeness** | All truths are provable.            |  

---

**Models: Consistency & Independence 📜**  
1. **Consistency:** Find *any* model → theory is non-contradictory.  
2. **Independence:** Find a model where $S$ is false → $S$ isn’t provable from the theory.  

**Example:**  
- Theory: $\forall x \forall y \, \text{Parent}(x, y) \rightarrow \neg \text{Parent}(y, x)$.  
- Model: Family tree where parents aren’t their own grandparents. 👪  

---


###  Standard Axiom Systems and Models 🔢  
1. **Peano Axioms** (`ℕ`): Defines natural numbers.  
2. **The integers(`Z`)**
3. **The rational numbers(`Q`)**: now we can divide
4. **Real Numbers (`ℝ`)**: Includes `√2`, π, etc.  
5. **The complex numbers(`C`)**
6. **Set Theory**: finite sets.  

---


**Final Thought:**  
*“Predicate logic: Where variables roam free and quantifiers rule!”* 🌐🔍  

--- 

