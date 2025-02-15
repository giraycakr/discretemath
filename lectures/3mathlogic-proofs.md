It will be edited...

---

# Mathematical Logic 🧠  
*"Modeling reality with simplicity."*

---

## Modeling Reality ↔️ Theory  
**Goal:** Simplify complex reality into mental models.  
- **Ideal Models:** Strip irrelevant details, keep essentials.  

| **Reality** 🌍 | → | **Model** 🧩 | → | **Theory** 📜 |  
|-----------------|---|--------------|---|----------------|  
| Piles of rocks 🪨 | → | `N = {0, 1, 2, ...}` | → | `∀x ∃y : y = x + 1` (Successor axiom) |  

**Big Models?** Use **axioms** and **inference rules** to build theories.  

---

## Axioms, Models, and Inference Rules ⚙️  

| Component | Description | Example 💡 |  
|-----------|-------------|-----------|  
| **Axioms** | Foundational truths | "All fish are green." 🐟 |  
| **Inference Rules** | Tools to derive truths | Modus Ponens: `P → Q, P ⊢ Q` |  
| **Theory** | All derivable statements | "George Washington is green!" 🎩 |  

---

# Proof Methods 🔍  
*Valid arguments to establish truth.*  

---

## Components of a Proof 🧩  
1. **Axioms/Theorems:**  
   - Always true in context.  
   - *Theorems* = Final results 🏁  
   - *Lemmas* = Intermediate results 🔄  
2. **Premises (P):** Assumptions for deriving consequences.  
3. **Inference Rules:** Derive conclusions (Q) from premises.  

**Game Analogy 🎮:**  
- **Start:** Axioms + Premises  
- **Rules:** Inference rules  
- **Goal:** Derive Q  

---

## Key Terms 📚  
| Term | Meaning |  
|------|---------|  
| **Hypothesis** | Unproven assumptions (axioms/premises) |  
| **Conclusion** | Final result derived from hypotheses |  

---

## Deducibility (`⊢`) vs. Implication (`→`) ⚖️  

| Symbol | Meaning | Example |  
|--------|---------|---------|  
| `P ⊢ Q` | Q is *provable* from P | "Given `P`, we can derive `Q` using rules." |  
| `P → Q` | Logical relationship | "If `P` is true, `Q` must be true." |  

### Soundness & Completeness 🎯  
- **Soundness:** If `P ⊢ Q`, then `P → Q` is a tautology. ✅  
- **Completeness:** If `P → Q` is a tautology, then `P ⊢ Q`. ✅  

---

## Inference Rules 🛠️  
*Tools to build valid arguments.*  

---

### Modus Ponens 🎯  
**Tautology:** `(P ∧ (P → Q)) → Q`  
**Example:**  
1. *Axiom:* "If it doesn’t fit, you must acquit." 👨⚖️  
2. *Premise:* "It doesn’t fit." 🧥  
3. *Conclusion:* "You must acquit." ⚖️  

---

### Argument Validity Example 🔢  
**Claim:**  
*"If √2 > 3/2, then (√2)² > (3/2)². Since √2 > 3/2, then 2 > 9/4."*  

| Component | Status |  
|-----------|--------|  
| **Premise P:** `√2 > 3/2` | ❌ False |  
| **Premise P→Q:** `√2 > 3/2 → 2 > 9/4` | ✅ True |  
| **Conclusion Q:** `2 > 9/4` | ❌ False |  

**Result:** Argument is **valid** (structure is sound) but **unsound** (P is false).  

---

### Mouse & Cookie Argument 🐭🍪  
1. *Axiom 1:* "If you give a mouse a cookie, he’ll ask for milk." 🥛  
2. *Axiom 2:* "If he asks for milk, he’ll want a straw." 🥤  
3. *Premise:* "You gave a mouse a cookie." 🍪  
4. *Conclusion:* "He wants a straw." 🥤  

**Flaw:** Axiom 1 is false (mice can’t ask for milk). 🚫  

---

## Common Inference Rules 📜  

| Rule | Format | Example | Emoji |  
|------|--------|---------|-------|  
| **Modus Ponens** | `P, P→Q ⊢ Q` | "Rain → Wet, Rain ⊢ Wet" ☔ | ✅ |  
| **Modus Tollens** | `¬Q, P→Q ⊢ ¬P` | "¬Wet, Rain→Wet ⊢ ¬Rain" 🌞 | ❌ |  
| **Hypothetical Syllogism** | `P→Q, Q→R ⊢ P→R` | "Study→Pass, Pass→Happy ⊢ Study→Happy" 😊 | 🔄 |  
| **Disjunctive Syllogism** | `P∨Q, ¬P ⊢ Q` | "Pizza∨Salad, ¬Pizza ⊢ Salad" 🥗 | 🍕 |  
| **Resolution** | `P∨Q, ¬P∨R ⊢ Q∨R` | "Rain∨Snow, ¬Snow∨Traffic ⊢ Rain∨Traffic" 🚗 | ⚖️ |  

---

**Final Thought:**  
*“Logic is the backbone of truth—build your arguments wisely!”* 🏗️✨  

--- 
