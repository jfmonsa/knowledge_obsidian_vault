# Predicate Logic
+ a.k.a. First-order logic, predicate calculus, quatificational logic
+ First-order logic uses quantified variables over non-logical objects, and allows the use of sentences that contain variables.
+ Propositional Logic is the basis of First-order logic, First-order logic adds **predicates** and  **quatifiers**
+ **Predicate (formula)**: statements involving variables, que puede conectar con una o varias expresiones para formar una oración. Los predicados son ==Tratados como funciones==. e.g $\text{isPhilosopher(x)}$
+ **Thre truth value of a formula ...** The truth of a formula such as "_x_ is a philosopher" depends on which object is denoted by _x_ and on the interpretation of the predicate "is a philosopher". (==variables = subjects==)
+ Relationships between predicates can be stated using logical connectives. e.g. "if _x_ is a philosopher, then _x_ is a scholar"
+ **Quantifiers** are applied to variables in a formula
	+ **Existencial**: $\exists$ (exists) $\exists x P(x)$ There exists an element x in the domain such that $P(x)$ is true
	+ **Universal**: $\forall x P(x)$, $P(x)$ is true for all values of $x$ in the domain. to prove false find a counter example
+ **Domain of discourse**: the entities that can instatiate the variables

> A theory about a topic, such as set theory, a theory for groups,[[3]](https://en.wikipedia.org/wiki/First-order_logic#cite_note-Tarski53-3) or a formal theory of [arithmetic](https://en.wikipedia.org/wiki/Arithmetic "Arithmetic"), is usually a first-order logic together with a specified [domain of discourse](https://en.wikipedia.org/wiki/Domain_of_discourse "Domain of discourse")

> The domain of discourse _D_ is a ==nonempty set of "objects"== of some kind. Intuitively, given an interpretation, a first-order formula becomes a statement about these objects; for example, $\exists x P(x)$ states the existence of some object in _D_ for which the predicate _P_ is true

## Qualifiers with restricted domain
![[Pasted image 20241125235107.png]]
## Logical Equivalences (Quantifiers)
![[Pasted image 20241125235322.png]]

## Inferencia en Logica de Predicados
+ Terminos base == constants
+ Dos reglas nuevas de inferencia: Eliminación universal, Eliminación existencial
### Eliminación Universal
![[Pasted image 20241126000116.png]]

![[Pasted image 20241126000154.png]]
+ Aplicando la sustitución universal
![[Pasted image 20241126000259.png]]

## Eliminación Existencial
![[Pasted image 20241126000353.png]]
+ Aplicando la elminaciń existencial
![[Pasted image 20241126000419.png]]

## Ejemplos:
![[Pasted image 20241126000536.png]]
+ (ignorar 3 xd) -> aplicamos elimin-universal(2) a (l1) y Modus Ponens(2,4) (l3)
![[Pasted image 20241126000559.png]]
