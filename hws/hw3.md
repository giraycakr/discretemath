# Homework-3 Algorithms and Induction

## Questions

1. **Big-Oh notasyonunda aşağıdaki algoritmanın işlem (toplama ve çarpma) sayısını gösteriniz.**  
   Give a big-O estimate for the number of operations (where an operation is an addition or a multiplication) used in this segment of an algorithm.

   ```plaintext
   t := 0
   for i := 1 to n
     for j := 1 to 2n
       t := t + ij
   ```

---

2. **Big-Oh notasyonunda aşağıdaki algoritmanın işlem (toplama ve çarpma) sayısını gösteriniz.**  
   Give a big-O estimate for the number of operations (where an operation is an addition or a multiplication) used in this segment of an algorithm.

   ```plaintext
   t := 0
   for i := 1 to n
     for j := i to 2n
       t := t + ij
   ```
---

3. **Her bit işlemi $10^{-11}$ saniyede gerçekleşiyorsa, aşağıda çalışma zamanları farklı f(n) bit işlem olarak verilen algoritmalarda, bir günde çözülebilecek en büyük $n$ değerlerini hesaplayınız.**  
   If each bit operation is carried out in $10^{-11}$ seconds; what is the largest $n$ for which one can solve within a day using an algorithm that requires the following $f(n)$ bit operations

   - **(a) $\log n$**  

   - **(b) $n^2$**  

   - **(c) $n^3$**  

   - **(d) $2^n$**  

   - **(e) $n!$**  

---

4. **$(3x^2 + x + 1)$'in $\Theta(x^2)$ olduğunu gösteriniz.**  
   Show that $3x^2 + x + 1$ is $\Theta(x^2)$.


---

5. **$x^3$'ün $O(x^4)$ olduğunu ve $x^4$'ün $O(x^3)$ olmadığını gösteriniz.**  
   Show that $x^3$ is $O(x^4)$ but $x^4$ is not $O(x^3)$.

---

6. **25 ve 40 dolarlık hediye çekleriyle oluşturulabilecek toplamları belirleyiniz (strong induction ile ispatlayınız).**  
   *Determine the possible total amounts using 25 and 40 dollar gift certificates. Prove using strong induction.*



---

7. **$a_0 = 1$, $a_1 = 2$, $a_n = a_{n-2} + a_{n-1}$ dizisi için $a_n \leq 2^n$ olduğunu gösteriniz.**  
   *Show that $a_n \leq 2^n$ for the sequence defined by $a_0 = 1$, $a_1 = 2$, and $a_n = a_{n-2} + a_{n-1}$.*

---


8. **Aşağıdaki geometrik serinin kapalı formülünü bulunuz (tahmin yöntemini kullanabilirsiniz) ve tümevarımla ispatlayınız:**  
    Find (you can give values to guess) and prove the closed-form formula for the geometric series:
```math
\sum_{k=1}^n k^2 = 1^2 + 2^2 + 3^2 + \dots + n^2
```

---

9. **Aşağıdaki geometrik serinin kapalı formülünü bulunuz ve tümevarımla ispatlayınız:**  
    Find and prove the closed-form formula for the geometric series:
```math
\sum_{k=0}^n ar^k = a + ar + ar^2 + \dots + ar^n \quad (r \neq 1)
```
---

10. **Recursive Decision Trees (Induction):**  
    A decision tree splits a dataset of size $n$ into two subsets of size $\lfloor n/2 \rfloor$ and $\lceil n/2 \rceil$ at each node.  
    **Task:** Use induction to prove that the maximum depth of the tree is $O(\log n)$. 

---

11. **Algorithm Analysis (Recursion):**  
    A recursive AI algorithm for generating all possible paths in a grid is defined as follows:  
    ```python
    def count_paths(m, n):
        if m == 1 or n == 1:
            return 1
        return count_paths(m-1, n) + count_paths(m, n-1)
    ```  
    **Tasks:**  
    - **(a)** Give a Big-Oh estimate for the time complexity of this algorithm.  
    - **(b)** Prove by induction that `count_paths(m, n)` correctly computes the number of unique paths in an `m x n` grid.  

---

12.  **Induction in Neural Networks:**  
A simple neural network layer computes $f(x) = ReLU(Wx + b)$, where $W$ is a weight matrix and $b$ is a bias vector. ReLU is the rectified linear unit, which outputs x if x is positive, otherwise 0.
```math
ReLU(x) = x^+ = \max(0, x) = \frac{x+|x|}{2} = \begin{cases}
x & \text{if } x > 0, \\
0 & x \le 0\end{cases}
```    
Suppose $f^{(k)}(x)$ denotes applying f, k times recursively.  
**Task:** Prove by induction that if all weights in $W$ are non-negative, then $f^{(k)}(x)$ is non-decreasing for all $k \geq 1$.  

---

## Submission
Submit via canvas.
Do not put links.

## Grading Rubric
The homework is peer graded. 

- Each question is 10 points. For each question, the grading is as follows:
  - 0 missing answers
  - 5 insufficient or not totally related answer (unchecked AI output etc.)
  - 8 sufficient but not enough 
- **+20 points for peer reviewing**
- Total grade will be scaled back to 100.