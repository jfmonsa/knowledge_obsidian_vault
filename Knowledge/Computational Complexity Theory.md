+ determine the practical limits on what computers can and cannot do.
+ P vs NP (milenium prize problems)
---
+ Asymptotic notation
+ A [computational problem](https://en.wikipedia.org/wiki/Computational_problem "Computational problem") can be viewed as an infinite collection of _instances_ together with a set (possibly empty) of _solutions_ for every instance.

# Clasification of problems
+ Solution problems: e.g. Find all posible combinations of $S$ set such as the sum of all elements is equal to $P$
+ Decision problems: e.g. find if there is a hamiltonian path in a graph
+ Optimization problems: e.g. Travelling salesman problem

# Turing Machines
+ A Turing machine is a mathematical model of a general computing machine.
+ theoretical device that manipulates symbols contained on a strip of tape
+ Turing machines are not intended as a practical computing technology, but rather as a general model of a computing machine—anything from an advanced supercomputer to a mathematician with a pencil and paper.
+ It is believed that if a problem can be solved by an algorithm, there exists a Turing machine that solves the problem
+ Many types of Turing machines: deterministic, probabilistic, non-deterministic, quatum, etc.

## Complexity Measure
+ he time required by a deterministic Turing machine $M$ on input $x$  is the total number of state transitions, or steps, the machine makes before it halts and outputs the answer ("yes" or "no").

# Complexity Classes
+ Many important complexity classes can be defined by bounding the time or space used by the algorithm.
![[Pasted image 20250224231552.png]]



A problem that can theoretically be solved, but requires impractical and finite resources (e.g., time) (NP-hard, exponential)
Conversely, a problem that can be solved in practice is called a _**tractable problem**_ P-TIME