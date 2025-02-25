# Intro
+ Is a formal computational model, programming paradigm, a set of techniques for solving CSPs
+ involves defining a problem in terms of **variables**, **domains** (finite domains) and **constraints** the it is solved by a **Constraint Solver**
+ Constraint solver is a software that explore possibles values of those variables using techniques such as backtracking, constraint propagation, heuristics, etc.
+ CP is incorporated through libraries for mainstream languages (python, java etc...) or DSL (_Domain Specific Languages_) such as prolog
---
+ the ability to formulate our problem in terms of _variables_, _constraints_ and _solutions_ instead of algorithms and procedures.

## Use cases
+ Scheduling problems, optimization problems, combinatorics, operations research, sequence  problems, allocation problems (are **Constraint Satisfaction Problems**)
+ http://www.csplib.org/ good collection of those problems
+ Useful for problems where solution space is large and complex
## References
+ Principles of Cosntraint Programming - Krzysztof R. Apt. (BOOK)
+ Concepts, Techniques, and Models of Computer Programming (BOOK)
# Constraint Satisfaction Problems (CSP)
+ Given:
	+ A set of **desicion variables**
	+ For each desicion variable, a **domain** of potential values.
	+ A set of **constrains** on the desicion variables
+ Find
	+ An **assigment** of values to variables such that all constrainst are satisfied
---
Principles of Constraint Programming - Chapter 2
# Constraint Optimization Problems
+ Given
	+ A CSP plus an **objective function**
	+ Such as maximizing or minimazing the value of some variable or the objective function (expression)
+ Find
	+ Assignment of values to variables such as
		+ All constraints are satisfied
		+ The objective is optimised
# Modeling & Representation: ¿How to model the problem?
+ CP is declarative
+ Effort is spent describing the problem, not solving it
+ Representation of problems is a big part of constraint programming
	+ Constraint programming languages work on finite domains for variables
	+ variables usually have limited valid types, such as just integer, boolean and sequences (not floating points since ithey have infinite domain)
+ Symmetry is also very important (??)
---
+ aspects of modeling:
	+ several natural representations exist
	+ some representations are straightforward others are not trivial
	+ some representations rely on a "background"
# Example
 How can I make a rectangle out of 24 unit squares so that the perimeter is
exactly 20?

**Constraints**
1. This local constraints are propagators
+ $x * y = 24$
+ $x+y=10$
+ $x \leq y$
2. Basic constraints (variable in explicit state which can be represented directly in memory)
+ $x \in  \{1,2, \dots , 9\}$
+ $y \in  \{1,2, \dots , 9\}$
**Computation Space**: contains propagators and basic constraints
$S_1 : X * Y =: 24 \land X+Y =: 10 \land X \leq Y \mid X \in \{1,\dots, 9\} \land Y \in \{1, \dots , 9\}$

Solution:
$Y= 6 \land X=4$

---
+ Each propagators make local deductions updating (narrowing) the computation space
+ When propagators can not keep narrowing computation space, we say that computation space has become **stable**, then the solver starts guessing (Domain cannot be reduced)


---
+ A programming laguage favors certains things
+ Concepts organized in terms of computation models
+ A computation model is formal system that defines how computations are done (computational model as a concept clarifies the definitions of programming paradigm)
+ Civilization is built on-top successful abstractions
+ Kernel language as a concept (core constructs of programming language)
+ each programming model has its own domain of application
**The limits of single models**
+ Good programming style requires using programming concepts that are usually associated with different computation models
+ OPP UI components are counter-intuitive e.g. Java Swing (Overuse of inheritance)
+ Functional programming encourage the over-use of higher-order programming. e.g. monads, currying
+ Logic languages overuses Horn clauses

**The Discipline in Programming**
1. Concepts and techniques
2. Algos and DS
3. Program design and software engineering
