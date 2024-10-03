+ Algos Búsqueda NO informada son: más costosos en tiempo
---
+ Heurísticas
+ Algoritmos de búsqueda informada
	+ Búsqueda Avara
	+ Algoritmo A*

# Función Heuristica

+ Una función que asigna a cada nodo ==el costo estimado a llegar a la meta== estando en dicho nodo
+ Se denota $h(n)$
+ ==Estima el valor real==
+ El valor de $h$ en la meta es 0, entre más cerca un nodo esta a la solución, el valor de su heuristica es menor
![[Pasted image 20240917074243.png]]

+ Las heurísticas son criterios para ==decidir cuál entre varias acciones promete ser la mejor== para alcanzar una meta
+ El uso de heuristicas en los algos de búsqueda, ==permiten reducir el espacio de estados a expandir en la construcción del árbol==

**Ejemplo**
+ El análisis clínico es de tipo heurístico, se da una estimación de su estado actual respecto a la meta que corresponde una persona saludable -> no es 100% seguro

### Algunas Heuristicas Por Juego
Ideas iniciales, luego veremos que existen heuristicas mejores que otras

**8-puzzle**
+ $h(n)$: cantidad de placas en posición incorrecta
+ Otra posible heuristica es una diferencia de matrices
![[Pasted image 20240917074425.png]]

**Problema de las 8 reinas**
![[Pasted image 20240917074459.png]]

**Misioneros y canibales**
![[Pasted image 20240917074534.png]]

**Mapa de Rumania**
![[Pasted image 20240917074610.png]]

**Ratón inteligente**
![[Pasted image 20240917075254.png]]
+ para problemas de laberintos se usa la distancia manhattan
# Estrategias de Busqueda Informada

Existen 2:
## 1 - [[AI - informed search - Estrategia Avara (Greedy)]]

## 2 - [[AI - informed search -  A star algo]] (A*)

# Heuristica admisible
+ A* es completo y optimo si se cumple con que la heuristica $h(n)$ sea admisible
$$ h(n)\leq costo\_real(n)$$
+ También se conocen como ==heuristicas optimistas==
----
Algunas Heuristicas Admisibles:

+ **8-puzzle**: 
	+ n placas en posición incorrecta, sin incluir la placa vacia
	+ **Mejor** Suma de las distancias Manhattan de cada pieza a su posición correcta (sin incluir el espacio vacio)
+ **Aros mágicos, triangulo magico**, etc: $n$ de lados que no suman $x$ dividido $y$ máximo lados afectados al hacer un intercambio

# Heuristica Dominante
+ Si para todo nodo n, $h_2(n) \geq h_1(n)$ se dice que h2 domina a h1

![[Pasted image 20240926203826.png]]
![[Pasted image 20240926203908.png]]
![[Pasted image 20240926212849.png]]
![[Pasted image 20240926213135.png]]