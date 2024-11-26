#index
+ [[Induction Proofs]]
+ [[Set Theory]]

# Notes
+ DM - Logica Proposicional Intro
+ DM - Logica Proposicional - Reglas de Inferencia
+ DM - Logica de Predicados
# Resources
+ Book of Proofs
# Sistema Formal (Sistema Logico)
+ Sistema abstracto compuesto por: **Lenguaje Formal**, **axiomas**, **reglas de inferencia** y a veces una **semantica formal**, que se utiliza para demostrar teoremas.
+ formalización rigurosa y completa del concepto de sistema axiomático
+ Al crear un sistema formal se pretende capturar y abstraer la esencia de determinadas características del mundo real, en un modelo conceptual expresado en un determinado lenguaje formal

# Propositional Logic
+ a.k.a: (Propositional calculus, first-order propositional logic, statement logic, setential calculus, sentential logic, zeroth-order logic)
+ Deals with **propositions** (which can be true or false) and relations between propositions
+ is typically studied with a [formal language](https://en.wikipedia.org/wiki/Formal_language "Formal language"), in which propositions are represented by letters (**propositional variables** or **atomic formulas**). **compound propositions** or **molecular sentences**  are created by combining propositions with connectives
+ **Main  oprators**: $A \land B$ , $A \lor B$, $\lnot A$, $A \rightarrow B$ 
---
+ otros conceptos: **formulas bien formadas**, **metavariables**
## Arguments
e.g.
1.  Mañana es miércoles **o** mañana es jueves.
2.  Mañana **no** es jueves.
3.  **Por lo tanto**, mañana es miércoles
---
+ **Valid argument**: Es imposible que las **premisas** (1) y (2) sean verdaderas y la conclusión sea falsa
+ **valid argument !== true conclusion (_soundness_)**  si las premisas son falsas, entonces la conclusión también podría serlo.

## Notable Rules
+ doble negación
+ Idempotencia (Tautology) $V \land V = V$ y  $V \lor V = V$
+ Asociatividad
+ conmutativa
+ distributivas 
	+ $\alpha \land (\beta \lor \gamma) = (\alpha \land \beta) \lor (\alpha \land \gamma)$
	+ $\alpha \land (\beta \lor \gamma) = (\alpha \lor \beta) \land (\alpha \lor \gamma)$
+ Leyes de Morgan
+ Material Implication $\alpha \rightarrow \beta = \neg \alpha \lor \beta$ 
+ Transposition (contraposition) $\alpha \rightarrow \beta = \neg \beta \rightarrow \neg \alpha$
## Reglas de Inferencia
Una [regla de inferencia](https://es.wikipedia.org/wiki/Regla_de_inferencia "Regla de inferencia") es una [función](https://es.wikipedia.org/wiki/Funci%C3%B3n_matem%C3%A1tica "Función matemática") que va de conjuntos de fórmulas a fórmulas. 
+ **premisas**: conunto de formulas que la función toma como argumento
+ **conclusión**: conjunto de formulas que la función retorna

>On the basis of asumptions you derive conclusions
---
+ Use Gentzen notation 
$${\displaystyle {\frac {P\to Q,P}{Q}}} = \displaystyle P\to Q,P\vdash Q$$
---

![[Pasted image 20241125211938.png]]
![[Pasted image 20241125222142.png]]
![[Pasted image 20241125223020.png]]
+ Note:
	+ Addition == O-Introducción
	+ Conjunction == y-introducción
	+ Simpleification == y-eliminación
# Resources
+ https://es.wikipedia.org/wiki/L%C3%B3gica_proposicional#Dos_sistemas_formales_de_l%C3%B3gica_proposicional (ver como se construye un sistema formal de logica: alfabeto, Gramatica (gramatica bien formada, ¿como debería usar el alfabeto?), axiomas (verdades, para construir demostraciones ulteriores), Reglas de Inferencia
+ https://youtu.be/HcS4lqXxrV4?si=f8729RGjzcGm3r2P Reglas de Inferencia (Good, short video)
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
# TODO:
+ ejercicios: dada base de conocimiento convierta a notación de conjuntos y demuestre c
+ Concepto de base de conocimiento