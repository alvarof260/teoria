## Camino

Un camino / cadena en un digrafo es una secuencia finita de vértices unidos a aristas que:
- tienen un comienzo y un final de vértices.
- los arcos no son repetidos.
- cada arco parte del vértice que lo precede y llega al vértice que lo sucede.
![[Pasted image 20240626134851.png]]

La longitud de un camino es la cantidad de aristas en ese camino.

Un camino simple es si su primer vértice difiere del ultimo.

## Ciclo

Un ciclo es un camino que coincide su primer y ultimo vértice.

Un circuito simple o ciclo simple es un camino simple en el que
coinciden el primero y el último vértice.
![[Pasted image 20240626135137.png]]


## Grafo Conexo

Un grafo es conexo si cualquier vértice de G es alcanzable desde
cualquier otro vértice. Un vértice v es alcanzable desde w si hay una
cadena que los une.

Un grafo fuertemente conexo significa que dos vértices cualquiera del grafo. parte de su vértice y llega al otro.

Un digrafo es acíclico si no admite ningún ciclo. Un digrafo acíclico se
denota también con dag.

## ciclo Eureliano

Un ciclo euleriano es un ciclo que contiene todas las aristas del grafo a consideración.

un grafo conexo G admite un ciclo euleriano si y solo si todo vértice de G tiene grado par.

![[Pasted image 20240626140221.png]]

![[Pasted image 20240626140256.png]]

## Camino Eureliano

Un grafo G admite una cadena euleriana si tiene como máximo dos vértices de grado impar.

## Ciclo Halmitoniano

Un ciclo hamiltoniano es un ciclo simple (no repite vértices) que recorre todos los vértices del grafo.
![[Pasted image 20240626140426.png]]

## Problema de Camino Minimo

Dado un digrafo G, en el cual los arcos tienen un costo no negativos y dado un vértice origen, El problema es encontrar el camino de costo mínimo de vértice de origen a cada uno de los vértices restantes del grafo.

Este problema puede resolverse por un algoritmo Greedy llamado
ALGORITMO DE DIJKSTRA (1956).
Es un algoritmo que usa la técnica greedy

```
ALGORITMO DIJKSTRA (A,n,D,P)
Calcula el costo del camino de menor costo desde el vértice 1 a cada
vértice del grafo.
Con recuperación de camino
ENTRADA: n: número de vértices.
A: matriz de adyacencia con los costos positivos.
SALIDA: D: vector de distancias especiales.
P: vector del camino.
AUXILIARES: S: conjunto de vértices elegidos.
C: conjunto de vértices candidatos

P1. S <- { 1 } C <- { 2, 3, ..., n } P(1) <- 0
P2. Para i desde 2 hasta n hacer
		D( i ) <- A ( 1, i )
		P( i ) <- 1
P3. Repetir n-2 veces
		Elegir en C un vértice w tal que D ( w ) sea mínimo
		Agregar w a S
		Borrar w de C
		Para cada vértice v en C hacer
			Si (D ( w ) + A ( w , v )) < D ( v ) entonces
				D ( v )  D ( w ) + A ( w , v )
				P ( v )  w
P4. Fin
```

![[Pasted image 20240626141643.png]]

los costo de O grande [[O grande 2]]

- Matriz de adyacencia: Algoritmo de Dijkstra є O(n2)
- Con una cola de prioridad implementada con heap: Algoritmo de Dijkstra є O((a+n) log n

## Problema de todos los Caminos Mínimos

En el algoritmo llamado de Floyd se seleccionan los vértices en orden
secuencial para construir una matriz A de costos de caminos
mínimos paso a paso.

```
ALGORITMO FLOYD (C,n,A)
Encuentra el camino de costo mínimo entre cualquier par de vértices
del grafo.
ENTRADA:
n: número de vértices.
C: matriz de costos no negativos.
SALIDA:
A: matriz de costos de los caminos mínimos

P1. Para i =1 hasta n hacer
		Para j =1 hasta n hacer
			A(i,j) <- C(i,j)
P2. Para i =1 hasta n hacer
		A(i,i)  0
P3. Para k =1 hasta n hacer
		Para i =1 hasta n hacer
			Para j =1 hasta n hacer
				Si (A(i,k) + A(k,j) ) < A(i,j) entonces
					A(i,j)  A(i,k) + A(k,j)
P4. Fin.
```

## Clausura transitiva

consiste en determinar si existe o no camino entre dos vértices del grafo.

```
ALGORITMO WARSHALL (A,n,A+)
Calcula A+ la clausura transitiva de la matriz A de adyacencia del grafo
ENTRADA: n: número de vértices
A: matriz de adyacencia booleana
SALIDA: A+: clausura transitiva del grafo

P1. A+ <- A
P2. Para k desde 1 hasta n hacer
		Para i desde 1 hasta n hacer
			Para j desde 1 hasta n hacer
				A+(i,j)  A+(i,j) or ( A+(i,k) and A+(k,j) )
P3. Fin. 
```

![[Pasted image 20240626142151.png]]

## Orden Topologico

Dado un digrafo acíclico (dag), un orden topológico consiste en
ordenar sus nodos de manera que si existe un camino del vértice v
al vértice w, entonces v aparece antes de w en la clasificación.

![[Pasted image 20240626142316.png]]
