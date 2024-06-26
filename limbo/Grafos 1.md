---
Parcial: Parcial dos
Materia: Algoritmo y Estructura de Datos
tags:
  - estructura
cssclasses: []
---
# Grafo

- Es una estructura de datos no lineal.
- Tipos de grafos:
  - Dígrafos.
  - Grafo Dirigido.
- Es un conjunto de vértices unidos por un conjunto de arcos.

Se denota como:
==G = (V, E)==

donde V es un conjunto finito de elementos llamados vértices o nodos o puntos.

E seria las lineas o aristas.
Cada arista tiene la forma (v1,v2) donde v1 y v2 ∈ V.

## El grafo no dirigido

El par de vértices que representa una arista no tiene orden, por lo cual (v1, v2) y (v2, v1) se refiere a la misma arista.
se puede viajar de un vértice a otro y viceversa por una misma arista.

dos vértices son adyacentes cuando son extremos de un mismo arcos.

grado de un vértice es el numero de aristas que inciden en el, contado cada lazo por 2.

![[Pasted image 20240624001307.png]]

## El grafo dirigido

El par de vértices tiene orden, el par de vértices ordenados (v1, v2) representa una arista que tiene origen en v1 y como destino el vértice v2.

grado de entrada: es el numero de aristas que inciden en V.
grado de salida: es el numero de aristas de V.
grado de un vertice V: es la suma de grado de entrada y salida de V.

El grado de un vértice se denota gr(V)
Grado de un grafo es el máximo grado de sus vértices.
Un vértice es aislado si su grado es cero.

![[Pasted image 20240624002632.png]]

## Bucle o lazo

se denomina así a la arista que une un vértice consigo mismo.

![[Pasted image 20240624105406.png]]


un grafo sin bucle se denomina grafo simple.

## Arcos Paralelos

dos arcos son paralelos si tienen los mismos extremos. A un grafo paralelo se le llama multigrafo.

un grafo sencillo es un grafo que no tiene aristas paralelas.
![[Pasted image 20240624105532.png]]


## Grafo Regular

Un grafo regular es un grafo que tiene todos sus vértices con mismo grado.

## Grafo Completo

Un grafo se dice completo si cualquier par de vértices distintos son
adyacentes, son grafos con todas sus aristas posibles.

Esto es : G=(V,E) en el que ∀ u,v ∈ V, u≠v, (u,v) ∈ E

![[Pasted image 20240624112236.png]]

## Grafo Ponderado

Un grafo valuado o ponderado o con costos o con pesos es aquel
en que se agrega información a las aristas.
Es un grafo G=(V,E) acompañado de una función f : E -> TipoE,
donde Tipo E es un conjunto cuyas componentes se denominan
costos. [[Grafos 2]]

![[Pasted image 20240624112418.png]]

## Términos de Grafo 

Orden de un grafo: es el numero de vértices del grafo, se denota con
la letra n
Tamaño de un grafo: es el numero de aristas o arcos del grafo, se
denota con la letra a
Grafo denso: es aquel en que el numero de arcos se aproxima al
numero de vértices al cuadrado. Esto es a ≈ n 2 .
Grafo esparcido o Grafo disperso: es un grafo con pocos arcos.
Cuando a\<n logn.

## Implementacion de Grafo

Existen dos formas de implementar:
- Matriz de Adyacencia.
- Lista de Adyacencia.

La matriz de adyacencia es la representación mas directa de un grafo .
Sea G=(V,E) un grafo donde V= {v1 ,v2 ,...,vn } , la matriz de adyacencia
de G es una matriz A cuadrada de orden n, de elementos
booleanos, donde:
	A(i,j) = true si y solo si existe un arco de vi a vj .
	A(i,j) = false si y solo si no existe un arco de vi a vj .
También se puede representar A con ceros y unos:
	A(i,j) = 1 si y solo si existe un arco de vi a vj .
	A(i,j) = 0 si y solo si no existe un arco de vi a vj .
La matriz A es simétrica cuando se trata de un grafo no dirigido.
En el caso de un dígrafo no se puede hacer ninguna afirmación.

![[Pasted image 20240624112927.png]]

La matriz de adyacencia se puede usar para almacenar un valor de
otro tipo en lugar de un valor booleano.

Con esta representación se puede usar una matriz de adyacencia
con costo, donde A(i,j) es el rótulo o valor o costo del arco que
une el vértice vi con el vértice vj. Si no existe tal arco se hace la
convención de usar un valor especial constante por ejemplo infinito.

Sea G=(V,E) un grafo donde V= {v1,v2 ,...,vn } , la matriz de adyacencia
con costo de G es una matriz A cuadrada de orden n, donde:
	A(i,j) = costo si y solo si existe un arco de vi a vj .
	A(i,j) = ∞ si y solo si no existe un arco de vi a vj .

![[Pasted image 20240624113016.png]]

La matriz de adyacencia es una representación adecuada para grafos
densos, esto es, cuando el número de arcos es casi el número de
vértices al cuadrado:
							a≈n2
La matriz de adyacencia requiere almacenamiento proporcional a
O(n 2 ), aun cuando tenga muchas entradas nulas.
Si n es grande y el numero de arcos es pequeño, habrá que usar una
representación más conveniente en cuanto al uso de
almacenamiento. 

Para grafos esparcidos (no densos) es más adecuada una representación con listas de adyacencia.

En la representación con lista de adyacencia para cada vértice del
grafo se mantiene una lista de todos sus vértices adyacentes.

Esa lista se puede implementar con una lista enlazada o con un vector
de vértices adyacentes.

El grafo se representa generalmente por un vector A, donde cada
entrada A(k) es un puntero a la lista del vértice vk .

![[Pasted image 20240624113132.png]]

