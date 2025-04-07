to be edited.

**Slide 1: Number Theory (Sayılar Teorisi)**  
- Number theory studies natural numbers (ℕ) and their properties, especially divisibility.  
  - ℕ includes 0 and positive integers.  
  - ℕ⁺ = {n ∈ ℕ | n > 0}.  
- Natural numbers have commutative, associative properties for addition/multiplication, distributive property, and identity elements.  
- Integers (ℤ) include 0, positive, and negative numbers.  
  - ℤ⁺ = {n ∈ ℤ | n > 0}.  

---

**Slide 2: Divisibility (Bölünebilme)**  
- Only 0 and 1 have multiplicative inverses in natural numbers.  
- For natural numbers $n$ and $m \neq 0$, $n = qm$ may not always hold.  
- Notation: $m \mid n$ (m divides n).  
  - Example: $4 \mid 24$.  
  - Terminology: $4$ is a *divisor* of $24$; $24$ is a *multiple* of $4$.  

---

**Slide 3: Prime and Composite Numbers**  
- **Prime**: A number >1 divisible only by 1 and itself.  
- **Composite**: A number >1 that is not prime.  
- **Special Cases**: 0 and 1 are neither prime nor composite.  

---

**Slide 4: Divisibility Properties**  
1. If $d \mid m$ and $d \mid n$, then $d \mid (m+n)$.  
   *Proof*: $m = ad$, $n = bd$ ⇒ $m+n = (a+b)d$.  
2. If $d \mid n$ and $n \neq 0$, then $d \leq n$.  
3. All $d$ divide 0: $0 = 0 \cdot d$.  
4. If $d \mid m$ and $d \mid n$, then $d \mid mn$.  
5. If $p$ is prime, $p \mid ab$ ⇒ $p \mid a$ or $p \mid b$.  

---

**Slide 5: Division Algorithm**  
**Theorem**: For integers $n, m \neq 0$, there exist unique integers $q$ (quotient) and $r$ (remainder) such that:  
\[
n = qm + r \quad \text{where } 0 \leq r < |m|.
\]  
- For positive $m$: $q = \lfloor n/m \rfloor$.  
- For negative $m$: $q = \lceil n/m \rceil$.  

---

**Slide 6: Modular Arithmetic**  
- **Congruence**: $x \equiv y \mod m$ ⇨ $m \mid (x - y)$.  
- Properties:  
  - If $x \equiv x' \mod m$ and $y \equiv y' \mod m$, then $x + y \equiv x' + y' \mod m$.  
  - Modular arithmetic preserves addition.  

---

**Slide 7: Fundamental Theorem of Arithmetic**  
**Theorem**: Every integer >1 can be uniquely factored into primes (up to ordering).  
**Key Corollaries**:  
1. If $n$ is composite, it has a prime factor ≤ $\sqrt{n}$.  
2. There are infinitely many primes.  
3. For $a, b ∈ ℤ⁺$:  
\[
ab = \text{gcd}(a, b) \cdot \text{lcm}(a, b).
\]  

--- 

**Slide 8: Bézout’s Theorem**  
**Theorem**: If $a, b ∈ ℤ^+$, there exist integers $s, t$ such that:  
\[
\gcd(a, b) = sa + tb.
\]  
- **Bézout coefficients**: Integers $s, t$.  
- Example: $\gcd(6, 14) = 2 = (-2) \cdot 6 + 1 \cdot 14$.  

**Example**: Express $\gcd(252, 198) = 18$ as a linear combination:  
\[
\begin{align*}
252 &= 1 \cdot 198 + 54, \\
198 &= 3 \cdot 54 + 36, \\
54 &= 1 \cdot 36 + 18, \\
18 &= 54 - 1 \cdot 36 \\
&= 4 \cdot 54 - 1 \cdot 198 \\
&= 4 \cdot 252 - 5 \cdot 198.
\end{align*}
\]  

---

**Slide 9: Euclidean Algorithm**  
\[
\gcd(m, n) = 
\begin{cases}
n & \text{if } m = 0, \\
\gcd(n \mod m, m) & \text{if } m > 0.
\end{cases}
\]  
**Extended Euclidean Algorithm**: Finds $s, t$ for Bézout’s identity:  
\[
m's + n't = \gcd(m, n).
\]  

---

**Slide 10: Key Proofs**  
1. **If $\gcd(a, b) = 1$ and $a \mid bc$, then $a \mid c$:**  
   - Bézout: $sa + tb = 1 ⇒ sac + tbc = c$.  
   - Since $a \mid tbc$ and $a \mid sac$, $a \mid c$.  

2. **If prime $p \mid a_1a_2\dots a_n$, then $p \mid a_i$ for some $i$:**  
   - Unique prime factorization implies $p$ must divide one factor.  

---

**Slide 11: Linear Congruence**  
Solve $ax \equiv b \mod m$:  
1. Find modular inverse $\bar{a}$ of $a \mod m$ (exists if $\gcd(a, m) = 1$).  
2. Multiply both sides by $\bar{a}$: $x \equiv \bar{a}b \mod m$.  

**Example**: Solve $3x \equiv 4 \mod 7$:  
- Inverse of $3 \mod 7$ is $-2$ (since $3 \cdot -2 = -6 \equiv 1 \mod 7$).  
- $x \equiv (-2) \cdot 4 = -8 \equiv 6 \mod 7$.  

---

**Slide 12: Chinese Remainder Theorem (CRT)**  
**Theorem**: Let $m_1, m_2, \dots, m_k$ be pairwise coprime. The system:  
\[
\begin{align*}
x &\equiv n_1 \mod m_1, \\
&\vdots \\
x &\equiv n_k \mod m_k,
\end{align*}
\]  
has a unique solution modulo $M = m_1m_2\cdots m_k$.  

**Example**: Solve:  
\[
\begin{align*}
x &\equiv 2 \mod 3, \\
x &\equiv 3 \mod 5, \\
x &\equiv 2 \mod 7.
\end{align*}
\]  
*Solution*: $x = 23$ (smallest positive).  

---

**Slide 13: Euler’s Totient Function**  
- $\phi(m)$: Number of integers $1 \leq k < m$ with $\gcd(k, m) = 1$.  
- **Formulas**:  
  - Prime $p$: $\phi(p) = p - 1$.  
  - Prime power $p^k$: $\phi(p^k) = p^{k-1}(p - 1)$.  
  - Composite $m = \prod p_i^{e_i}$: $\phi(m) = \prod p_i^{e_i-1}(p_i - 1)$.  

---

**Slide 14: Euler’s Theorem**  
**Theorem**: If $\gcd(a, m) = 1$, then:  
\[
a^{\phi(m)} \equiv 1 \mod m.
\]  
**Fermat’s Little Theorem**: For prime $p$:  
\[
a^{p-1} \equiv 1 \mod p \quad (\text{if } p \nmid a).
\]  

---
**Slide 15: RSA Encryption**  
**Core Idea**: Security relies on the difficulty of factoring large primes.  
**Steps**:  
1. **Key Generation**:  
   - Choose distinct primes \(p\) and \(q\).  
   - Compute \(m = pq\) and \(\phi(m) = (p-1)(q-1)\).  
   - Select \(e\) such that \(\gcd(e, \phi(m)) = 1\).  
   - Find \(d\) (modular inverse of \(e\)): \(de \equiv 1 \mod \phi(m)\).  
   - **Public Key**: \((e, m)\). **Private Key**: \((d, m)\).  

2. **Encryption**: For message \(x\) (\(0 \leq x < m\)):  
   \[
   \text{Ciphertext } y = x^e \mod m.
   \]  

3. **Decryption**:  
   \[
   x = y^d \mod m.
   \]  

---

**Slide 16: RSA Proof Using Euler’s Theorem**  
**Why \(x^{de} \equiv x \mod m\)?**  
- **Case 1**: \(\gcd(x, m) = 1\):  
  By Euler’s Theorem:  
  \[
  x^{\phi(m)} \equiv 1 \mod m \implies x^{k\phi(m)+1} \equiv x \mod m.
  \]  
  Since \(de = 1 + k\phi(m)\), \(x^{de} \equiv x \mod m\).  

- **Case 2**: \(\gcd(x, m) \neq 1\):  
  - \(x\) is divisible by \(p\) or \(q\) (but not both, as \(x < m = pq\)).  
  - Assume \(p \mid x\). By Fermat’s Little Theorem:  
    \[
    x^{q-1} \equiv 1 \mod q \implies x^{k(p-1)(q-1)} \equiv 1 \mod q.
    \]  
  - Multiply both sides by \(x\):  
    \[
    x^{de} = x^{1 + k(p-1)(q-1)} \equiv x \mod q.
    \]  
  - Similarly, \(x^{de} \equiv x \mod p\). By CRT, \(x^{de} \equiv x \mod m\).  

---

**Slide 17: Summary of Number Theory Concepts**  
- **Divisibility & Primes**: Foundation for encryption and hashing.  
- **Modular Arithmetic**: Basis for cryptography (RSA, Diffie-Hellman).  
- **CRT**: Efficient solutions to systems of congruences.  
- **Euler’s Theorem**: Critical for RSA’s correctness.  
- **RSA**: Practical application of primes, modular arithmetic, and theorems.  

---

**Slide 18: Exercises for Practice**  
1. Find \(\gcd(315, 84)\) using the Euclidean Algorithm.  
2. Solve \(5x \equiv 2 \mod 11\).  
3. Use CRT to solve:  
   \[
   x \equiv 1 \mod 3, \quad x \equiv 4 \mod 5, \quad x \equiv 0 \mod 7.
   \]  
4. Compute \(\phi(60)\).  
5. Encrypt \(x = 7\) with RSA using \(p = 5\), \(q = 11\), \(e = 3\).  

---

**Slide 19: Answers to Exercises**  
1. \(\gcd(315, 84) = 21\).  
2. \(x \equiv 7 \mod 11\) (inverse of 5 mod 11 is 9).  
3. \(x = 21 \mod 105\).  
4. \(\phi(60) = \phi(2^2 \cdot 3 \cdot 5) = 2 \cdot 2 \cdot 4 = 16\).  
5. \(m = 55\), \(\phi(m) = 40\), \(d = 27\) (since \(3 \cdot 27 = 81 \equiv 1 \mod 40\)).  
   Encryption: \(7^3 \mod 55 = 343 \mod 55 = 13\).  

--- 

**End of Slides**


**Slide 1: Number Theory**  
- Number theory studies natural numbers and their properties, especially divisibility. Today, it also includes integers.  
- $\mathbb{N}$ includes zero and positive integers.  
- $\mathbb{N}^+$ is the set of positive natural numbers: $\{n \in \mathbb{N} \mid n > 0\}$.  
- Natural numbers have commutative and associative properties for addition and multiplication, distributive property, and identity elements.  
- $\mathbb{Z}$ includes zero and positive/negative integers.  
- $\mathbb{Z}^+$ is the set of positive integers: $\{n \in \mathbb{Z} \mid n > 0\}$.  

---

**Slide 2: Divisibility**  
- Except 0 and 1, no natural number has an inverse under addition or multiplication.  
- If $n$ and $m$ are natural numbers, $n$ may not always be divisible by $m \neq 0$ (i.e., $n = qm$ might not hold).  
- **Notation**: $m \mid n$ means "$m$ divides $n$" (or $m$ is a divisor/factor of $n$).  
  - Example: $4 \mid 24$ (4 is a divisor of 24; 24 is a multiple of 4).  

---

**Slide 3: Prime and Composite Numbers**  
- A number $> 0$ is **prime** if divisible only by 1 and itself.  
- A number is **composite** if it is not prime.  
- **Note**: 0 and 1 are neither prime nor composite.  

---

**Slide 4: Divisibility Properties**  
1. If $d \mid m$ and $d \mid n$, then $d \mid (m + n)$.  
   - *Proof*: $m = ad$, $n = bd$ $\implies m+n = (a+b)d$.  
2. If $d \mid n$ and $n \neq 0$, then $d \leq n$.  
   - *Proof*: $n = kd \geq d$ for $k \geq 1$.  
3. For all $d$, $d \mid 0$.  
   - *Proof*: $0 = 0 \cdot d$.  
4. If $d \mid m$ and $d \mid n$, then $d \mid mn$.  
   - *Proof*: $m = kd \implies mn = (kn)d$.  
5. If $p$ is prime, then $p \mid ab$ $\iff$ $p \mid a$ or $p \mid b$.  

---

**Slide 5: Division Algorithm**  
**Theorem**: For integers $n$ and $m \neq 0$, there exist unique integers $q$ (quotient) and $r$ (remainder) such that:  
$$n = qm + r \quad \text{where } 0 \leq r < |m|.$$  
- For positive $m$, $q = \lfloor n/m \rfloor$.  
- For negative $m$, $q = \lceil n/m \rceil$.  

---

**Slide 6: Modular Arithmetic**  
- **Congruence**: $x \equiv y \pmod{m}$ means $m \mid (x - y)$.  
  - Equivalently: $x = y + qm$ for some integer $q$.  
- **Properties**:  
  - If $x \equiv x' \pmod{m}$ and $y \equiv y' \pmod{m}$, then $x + y \equiv x' + y' \pmod{m}$.  
  - Modular arithmetic preserves addition and multiplication.  

---

**Slide 7: Fundamental Theorem of Arithmetic**  
1. Every integer $> 1$ can be uniquely factored into primes (up to ordering).  
2. If $n$ is composite, it has a prime factor $\leq \sqrt{n}$.  
3. There are infinitely many primes.  
4. For $a, b \in \mathbb{Z}^+$:  
   $$ab = \gcd(a, b) \cdot \text{lcm}(a, b).$$  

---

**Slide 8: Bézout’s Theorem**  
**Theorem**: For integers $a, b > 0$, there exist integers $s, t$ such that:  
$$\gcd(a, b) = sa + tb.$$  
- **Example**: $\gcd(6, 14) = 2 = (-2) \cdot 6 + 1 \cdot 14$.  
- **Extended Euclidean Algorithm** computes $s$ and $t$.  

---



**Slide 9: Example of Bézout’s Identity**  
**Problem**: Express gcd(252, 198) = 18 as a linear combination of 252 and 198.  
**Steps**:  
1. Euclidean algorithm divisions:  
   $$  
   \begin{align*}  
   252 &= 1 \cdot 198 + 54, \\  
   198 &= 3 \cdot 54 + 36, \\  
   54 &= 1 \cdot 36 + 18, \\  
   36 &= 2 \cdot 18.  
   \end{align*}  
   $$  
2. Back-substitute to express 18:  
   $$  
   18 = 54 - 1 \cdot 36 = 54 - 1 \cdot (198 - 3 \cdot 54) = 4 \cdot 54 - 1 \cdot 198.  
   $$  
   Substitute \(54 = 252 - 1 \cdot 198\):  
   $$  
   18 = 4 \cdot 252 - 5 \cdot 198.  
   $$  

---

**Slide 10: Euclidean Algorithm**  
- **Recursive definition**:  
  $$  
  \gcd(m, n) =  
  \begin{cases}  
  n & \text{if } m = 0, \\  
  \gcd(n \bmod m, m) & \text{if } m > 0.  
  \end{cases}  
  $$  
- **Extended Euclidean Algorithm**: Finds coefficients \(s, t\) such that:  
  $$  
  s \cdot m + t \cdot n = \gcd(m, n).  
  $$  

---

**Slide 11: Key Divisibility Proof**  
**Theorem**: If \(a, b, c \in \mathbb{Z}^+\), \(\gcd(a, b) = 1\), and \(a \mid bc\), then \(a \mid c\).  
**Proof**:  
1. By Bézout’s identity: \(sa + tb = 1\) for integers \(s, t\).  
2. Multiply both sides by \(c\): \(sac + tbc = c\).  
3. Since \(a \mid sac\) and \(a \mid tbc\), \(a \mid c\).  

---

**Slide 12: Prime Divisibility Property**  
**Theorem**: If \(p\) is prime and \(p \mid a_1 a_2 \dots a_n\), then \(p \mid a_i\) for some \(i\).  
**Proof**:  
- By uniqueness of prime factorization, \(p\) must appear in the factorization of at least one \(a_i\).  
- If not, rearranging factors would violate uniqueness.  

---

**Slide 13: Solving Linear Congruences**  
**Equation**: \(ax \equiv b \pmod{m}\).  
**Steps**:  
1. Check if \(\gcd(a, m) = 1\). If yes, \(a\) has an inverse modulo \(m\).  
2. Find \(\bar{a}\) (inverse of \(a\)) such that \(\bar{a} \cdot a \equiv 1 \pmod{m}\).  
3. Multiply both sides by \(\bar{a}\): \(x \equiv \bar{a} \cdot b \pmod{m}\).  

---

**Slide 14: Example of Linear Congruence**  
**Problem**: Solve \(3x \equiv 4 \pmod{7}\).  
**Solution**:  
1. Find inverse of 3 modulo 7: \(-2\) (since \(3 \cdot (-2) \equiv -6 \equiv 1 \pmod{7}\)).  
2. Multiply both sides by \(-2\):  
   $$  
   x \equiv (-2) \cdot 4 \equiv -8 \equiv 6 \pmod{7}.  
   $$  

---

**Slide 15: Chinese Remainder Theorem (CRT)**  
**Problem**: Find \(x\) such that:  
$$  
\begin{align*}  
x &\equiv 2 \pmod{3}, \\  
x &\equiv 3 \pmod{5}, \\  
x &\equiv 2 \pmod{7}.  
\end{align*}  
$$  
**Answer**: \(x = 23\) (smallest solution).  

---

**Slide 16: Chinese Remainder Theorem Statement**  
**Theorem**: Let \(m_1, m_2, \dots, m_k\) be pairwise coprime. The system:  
$$  
x \equiv n_i \pmod{m_i} \quad (i = 1, 2, \dots, k)  
$$  
has a **unique solution** modulo \(M = m_1 m_2 \cdots m_k\).  
**Construction**:  
1. Let \(M_i = M / m_i\).  
2. Find \(M_i^{-1} \pmod{m_i}\).  
3. Solution: \(x = \sum_{i} n_i M_i M_i^{-1} \pmod{M}\).  

---

Let me know if you'd like the final set of slides!

**Slide 17: Euler’s Totient Function**  
- **Definition**: $\phi(m)$ = number of integers in $\{1, 2, \dots, m-1\}$ coprime to $m$.  
- **Properties**:  
  - For prime $p$: $\phi(p) = p - 1$.  
  - For prime power $p^k$: $\phi(p^k) = p^{k-1}(p - 1)$.  
  - For coprime $m, n$: $\phi(mn) = \phi(m)\phi(n)$.  
- **Formula for composite $m$**:  
  If $m = p_1^{e_1}p_2^{e_2}\cdots p_k^{e_k}$, then:  
  $$  
  \phi(m) = m \prod_{i=1}^k \left(1 - \frac{1}{p_i}\right).  
  $$  

---

**Slide 18: Euler’s Theorem**  
**Theorem**: If $\gcd(a, m) = 1$, then:  
$$  
a^{\phi(m)} \equiv 1 \pmod{m}.  
$$  
**Proof**:  
- Let $\mathbb{Z}_m^* = \{z_1, z_2, \dots, z_{\phi(m)}\}$.  
- Multiplying all elements by $a$ permutes $\mathbb{Z}_m^*$ modulo $m$:  
  $$  
  \prod_{i=1}^{\phi(m)} z_i \equiv \prod_{i=1}^{\phi(m)} (a z_i) \equiv a^{\phi(m)} \prod_{i=1}^{\phi(m)} z_i \pmod{m}.  
  $$  
- Cancel $\prod z_i$ (since $\gcd(z_i, m) = 1$):  
  $$  
  a^{\phi(m)} \equiv 1 \pmod{m}.  
  $$  

---

**Slide 19: Fermat’s Little Theorem**  
**Corollary**: If $p$ is prime and $\gcd(a, p) = 1$, then:  
$$  
a^{p-1} \equiv 1 \pmod{p}.  
$$  
- Directly follows from Euler’s theorem since $\phi(p) = p - 1$.  
- **Example**: For $p = 5$ and $a = 2$:  
  $$  
  2^4 = 16 \equiv 1 \pmod{5}.  
  $$  

---

**Slide 20: RSA Encryption Overview**  
**Key Setup**:  
1. Choose two distinct primes $p$ and $q$.  
2. Compute $n = pq$ and $\phi(n) = (p-1)(q-1)$.  
3. Select $e$ such that $\gcd(e, \phi(n)) = 1$.  
4. Compute $d \equiv e^{-1} \pmod{\phi(n)}$.  

**Encryption**:  
- For message $x$ (with $0 \leq x < n$):  
  $$  
  \text{Ciphertext } c \equiv x^e \pmod{n}.  
  $$  

**Decryption**:  
- Recover $x$ using private key $d$:  
  $$  
  x \equiv c^d \pmod{n}.  
  $$  

---

**Slide 21: RSA Correctness Proof**  
**Proof**:  
- If $\gcd(x, n) = 1$, by Euler’s theorem:  
  $$  
  x^{\phi(n)} \equiv 1 \pmod{n}.  
  $$  
  Since $ed \equiv 1 \pmod{\phi(n)}$, write $ed = k\phi(n) + 1$:  
  $$  
  c^d \equiv x^{ed} \equiv x^{k\phi(n)+1} \equiv x \pmod{n}.  
  $$  
- If $\gcd(x, n) \neq 1$, use CRT:  
  - Show $x^{ed} \equiv x \pmod{p}$ and $x^{ed} \equiv x \pmod{q}$.  
  - Combine via CRT to conclude $x^{ed} \equiv x \pmod{n}$.  

---

**Slide 22: Example of RSA**  
**Key Generation**:  
- Let $p = 3$, $q = 11$, so $n = 33$ and $\phi(n) = 20$.  
- Choose $e = 3$ (since $\gcd(3, 20) = 1$).  
- Compute $d \equiv 3^{-1} \pmod{20} = 7$.  

**Encryption**:  
- Encrypt $x = 4$:  
  $$  
  c = 4^3 \equiv 64 \equiv 31 \pmod{33}.  
  $$  

**Decryption**:  
- Decrypt $c = 31$:  
  $$  
  x = 31^7 \equiv 4 \pmod{33}.  
  $$  

---

**Slide 23: Security of RSA**  
- Relies on the **difficulty of factoring large integers** $n = pq$.  
- Known attacks:  
  - Weak if $p$ or $q$ is small.  
  - Vulnerable to side-channel attacks (timing, power analysis).  
  - Requires padding (e.g., OAEP) to prevent chosen-ciphertext attacks.  

---

**Slide 24: Summary**  
1. Number theory underpins modern cryptography (e.g., divisibility, primes, CRT).  
2. Euler’s theorem and Fermat’s theorem enable modular exponentiation.  
3. RSA uses one-way functions (factoring vs. exponentiation) for secure communication.  
4. Always use large primes and secure implementations for RSA.  

---  

**Slide 25: Hashing and Number Theory**  
- **Mersenne Primes**: Primes of the form \(2^p - 1\) where \(p\) is prime.  
  - Examples: \(3 = 2^2 - 1\), \(7 = 2^3 - 1\), \(127 = 2^7 - 1\).  
  - Computational advantage: Efficient modular arithmetic due to binary-friendly structure.  
- **Role in Hashing**:  
  - Used in some hash functions (e.g., Mersenne Twister PRNG for seeding).  
  - Potential for modulus operations: \( \text{hash}(x) = (ax + b) \mod (2^p - 1) \), leveraging fast bitwise operations.  

---

**Slide 26: Prime Modulus in Hashing**  
- **Prime Modulus**: Reduces collisions by ensuring uniform distribution.  
  - Hash tables often use prime-sized buckets.  
  - Example: \( \text{hash}(k) = k \mod m \), where \(m\) is prime.  
- **Double Hashing**: Uses primes to resolve collisions:  
  $$  
  h(k, i) = (h_1(k) + i \cdot h_2(k)) \mod m,  
  $$  
  where \(h_2(k)\) and \(m\) are coprime (ensured via primes).  

---

**Slide 27: Polynomial Rolling Hash**  
- **Number Theory Basis**: Treats strings as coefficients of a polynomial.  
  - For string \(s = s_0 s_1 \dots s_n\), compute:  
    $$  
    \text{hash}(s) = \sum_{i=0}^n s_i \cdot a^{n-i} \mod p,  
    $$  
    where \(a\) is a constant (e.g., 31) and \(p\) is a large prime (e.g., Mersenne prime).  
- **Collision Resistance**: Depends on choice of \(a\) and \(p\) (primes improve uniformity).  

---

**Slide 28: Cryptographic Primes in Hashing**  
- **Safe Primes**: Primes \(p = 2q + 1\) (where \(q\) is prime), used in hash-based cryptography.  
- **Sophie Germain Primes**: Primes \(q\) where \(2q + 1\) is also prime.  
- **Applications**:  
  - Key derivation functions (e.g., PBKDF2).  
  - **Mersenne Primes** in lattice-based cryptography (post-quantum security).  

---

**Slide 29: Theoretical Limits and Open Problems**  
- **Collision Resistance**: Tied to the difficulty of solving equations modulo primes.  
  - Example: Finding \(x \neq y\) such that \(H(x) \equiv H(y) \mod p\).  
- **Unsolved Questions**:  
  - Are there infinitely many Mersenne primes? (Only 51 known as of 2023).  
  - Can hash security be proven under number-theoretic conjectures (e.g., Riemann Hypothesis)?  

---  

**End of Slides**