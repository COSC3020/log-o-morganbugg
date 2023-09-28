[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12115816&assignment_repo_type=AssignmentRepo)
# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

---
### Answer

Here, we substitute $\log_2(n)$ in place of $f(n)$ to start the first half of this proof. </br>
$T(n) \in O(\log_2(n)) \iff \exists c, n_0: T(n) \leq c \cdot \log_2(n) \forall n \geq n_0$ </br>
Next, we use the change of base rule. </br>
$T(n) \leq c \cdot (\frac{1}{\log_5(2)}) \cdot \log_5(n)$ </br>
We can then simplify to this expression where k is a constant </br>
$T(n) \leq k \cdot \log_5(n)$ </br>
-> $T(n) \in O(\log_5(n))$

We can then follow this same reasoning for the second half. </br>
$T(n) \in O(\log_5(n)) \iff \exists c, n_0: T(n) \leq c \cdot \log_5(n) \forall n  \geq n_0$ </br>
$T(n) \leq c \cdot (\frac{1}{\log_2(5)}) \cdot \log_2(n)$ </br>
$T(n) \leq k \cdot \log_2(n)$ </br>
-> $T(n) \in O(\log_2(n))$

Since we have proven both of these statements, we know that $O(\log_{2} n)$ is the same as $O(\log_{5} n)$

### Extra

If we wanted to prove the same for $\Theta(\log_2(n))$ and $\Theta(\log_5(n))$, we could do the following:

$T(n) \in \Omega(\log_2(n)) \iff \exists c, n_0: T(n) \geq c \cdot \log_2(n) \forall n  \geq n_0$ </br>
$T(n) \geq c \cdot (\frac{1}{\log_5(2)}) \cdot \log_5(n)$ </br>
$T(n) \geq k \cdot \log_5(n)$ </br>
-> $T(n) \in \Omega(\log_5(n))$

$T(n) \in \Omega(\log_5(n)) \iff \exists c, n_0: T(n) \geq c \cdot \log_5(n) \forall n  \geq n_0$ </br>
$T(n) \geq c \cdot (\frac{1}{\log_2(5)}) \cdot \log_2(n)$ </br>
$T(n) \geq k \cdot \log_2(n)$ </br>
-> $T(n) \in \Omega(\log_2(n))$

Once we have proved the Big Omega and Big O in both directions, we can determine that, by definition, Big Theta holds true.