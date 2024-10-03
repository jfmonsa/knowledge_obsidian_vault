+ **Key Idea**: So, suppose that you model the running time of a program as a function $f(n)$, (often named as $T(n$)) where $n$ is some measure of the size of the input problem 
+ Describe the behavior of an algorithm's runtime or resource usage as a function of the input size.
+ The asymptotic notations describe bounds of the grow rate of space complexity and time complexity

# Simplification rules for $T(n)$:
**Key Ideas**
* Ignore multiplicative constants
* Ignore behavior on small inputs, concentrating on how well programs handle large inputs. (Aka asymptotic analysis.)
**Rules**
- If _f_(_x_) is a sum of several terms, if there is one with largest growth rate, it can be kept, and all others omitted.
- If _f_(_x_) is a product of several factors, any constants (factors in the product that do not depend on x) can be omitted
- We only consider the most significant term of $f(n)$ because as $f(n)$ grows for larger values of $n$ ($n$ tends to infinity) the other terms are not significant
**Summary**
+ We’ll consider functions such as $3x^2$, $47x²+x$ , and $0.03x²+5947+x+log(x)$ to all grow at the same rate. Similarly, functions
+ such as $3x/2$, $47/65x$, and $0.03x$ will be treated as growing at the same, slower, rate

# 1 -  Big-O  (oh) notation $O(n)$
+ Big-O notation represents the upper bound of the running time of an algorithm (Cota superior)
+ Therefore, it gives the ==worst-case complexity of an algorithm==
+ Notation Example:  $T(n)=O(n^2)$ or $T(n) \in O(n^2)$ 
+ if $c*g(x)$ is a ==tight upper-bound== of $f(x)$ we say that $f(x) \in O(g(x))$

![[Pasted image 20240630100932.png]]
# 2 - Omega Notation $\Omega(n)$
+ Omega notation represents the ==lower bound== of the running time of an algorithm.
+ Thus, it provides the ==best case complexity== of an algorithm.
+ If g is a lower bound, the execution times are always above this bound
+ if $c \cdot g(n)$ is a tight lower-bound of $f(n)$ we say that $f(x) \in \Omega (n)$ 

![[Pasted image 20240630101459.png]]
# 3 - Theta Notation $\theta(n)$
+ When we say that an algorithm is $Θ(g(n))$, we are saying that g(n) ==is both a tight upper-bound and a tight lower-bound on the growth== of the algorithm’s effort.
+ $f(n) \in \Theta (g(n))$ si $f(n) \in O(g(n))$ y $f(n) \in \Omega ( g(n))$
+ ==Average-case==

![[Pasted image 20240630100717.png]]

# 4 - Small o (little-o) Notation $o(n)$
+ upper-bound that cannot be tight ==(loose upper bound)==
+ if $c*g(x)$ is a ==loose upper-bound== of $f(x)$ we say that $f(x) \in O(g(x))$
$$0 \leq f(n) \leq c \cdot g(n)$$
# 5 - Small Omega (little omega) $\omega (n)$
+ loose lower bound
$$0 \leq f(n) > c \cdot g(n)$$
# Formal Definitions

## Big-O
The formal definition of Big O notation is as follows:

Let $f(n)$ and $g(n)$ be functions that map positive integers to positive real. We say that $f(n)$ is $O(g(n))$ (read as "$f$ of $n$ is Big O of $g$ of $n$") if there exist positive constants $c$ and $n_0$ such that for all $n \geq n_0$, ($n_0>=1$) the following inequality holds:
$$0 \leq f(n) \leq c \cdot g(n)$$
In other words, $f(n)$ is bounded above by $g(n)$ multiplied by a constant factor $c$ for sufficiently large values of $n$. This notation is used to describe the upper bound of an algorithm's running time, indicating that the growth rate of $f(n)$ will not exceed that of $g(n)$ by more than a constant factor as $n$ becomes large.

## Little-O

(Little–o, $o()$): Let $f(n)$ and $g(n)$ be functions that map positive integers to positive real numbers. We say that $f(n)$ is $o(g(n))$ (or $f (n) ∈ o(g(n))$) if for any real constant $c > 0$, there exists an integer constant $n_0 ≥ 1$ such that $f(n) < c ∗ g(n)$ for every integer $n ≥ n0.$
$$0 \leq f(n) < c \cdot g(n)$$
## Big Omega
(Big–Omega, $Ω())$: Let f (n) and g(n) be functions that map positive integers to positive
real numbers. We say that f (n) is Ω(g(n)) (or f (n) ∈ Ω(g(n))) if there exists a real constant c > 0 and there exists an integer constant n0 ≥ 1 such that f (n) ≥ c · g(n) for every integer n ≥ n0
## Little - Omega
(Little–Omega, ω()): Let f (n) and g(n) be functions that map positive integers to positive
real numbers. We say that f (n) is ω(g(n)) (or f (n) ∈ ω(g(n))) if for any real constant c > 0, there exists an integer constant n0 ≥ 1 such that f (n) > c · g(n) for every integer n ≥ n0.
## Big Theta
(Big–Theta, Θ()): Let f (n) and g(n) be functions that map positive integers to positive
real numbers. We say that f (n) is Θ(g(n)) (or f (n) ∈ Θ(g(n))) if and only if f (n) ∈ O(g(n)) and
f (n) ∈ Ω(g(n))
## About Sets
Formally $O(n)$ and $\Omega(n)$ represent sets of  functions because there are multiple functions that can be upper and lower bound for a given $f(x)$ function

Formally, the big-o notation represents a set of functions that bound above $f(x)$: (All notation actually define a set of functions that bounds or $f(x)$ function)
$$O(g(n)) = \{ f(n) : \text{ if and only if } \exists c > 0 \text{ and } n_0 \geq 0 \text{ such that } \forall n \geq n_0, 0 \leq f(n) \leq c \cdot g(n) \}$$
For example: 
$$O(x²) = \{ x, x^{1/2},log(x), 1 \}$$
![[Pasted image 20240630095217.png]]

## Summary
![[Pasted image 20240711002741.png]]
![[Pasted image 20240711002754.png]]
# Proving The Relationship of a function
## 1 - By Definition
## 2 - Using Induction
## 3 -  With Limits

# Some important notes

# Resources
Profundizar más
+ https://mfleck.cs.illinois.edu/building-blocks/version-1.2/big-o.pdf
+ https://www2.cs.arizona.edu/classes/cs345/summer14/files/bigO.pdf