La definición del recorrido relacionado a una estructura de un grafo es mucho mas compleja que para una lista o un árbol por las siguientes razones:
- No existe un nodo inicial.
- No hay un orden entre los sucesores de un nodo particular.
- Un nodo puede tener mas de un predecesor.

Existe dos tipo de recorrido en un grafo:
- DFS: En profundidad (Depth First Search)
- BFS: En Amplitud (Breadth First Search)

## En profundidad

El recorrido de profundidad de los vértices de un grafo tiene este funcionar:
- Se comienza de un vértice V, se marca como visitado y busca un vértice W que sea adyacente a V que no haya sido visitado.
- Cuando un vértice U tiene vértices adyacentes ya visitado, se cierra ese vértice y se vuelve para atrás a buscar otro vértice adyacente(si este tiene vértice no visitado).
- La búsqueda se termina cuando ya no quede ningún vértice sin visitar.

Este recorrido tiene una forma recursiva.

```
Algoritmo RecorridoEnProfundidad (G)
ENTRADA: G: GRAFO de vértices numerados
SALIDA: listado de vértices
Global: visitado: arreglo con dominio en vértices y valores bool
P1. PARA cada vértice v de G HACER
		visitado (v) <- falso
P2. PARA cada vértice v de G HACER
		SI NOT visitado ( v ) ENTONCES
			dfs ( v )
P3. FIN
```

```
ALGORITMO dfs (v)
ENTRADA: vértice v no visitado
SALIDA: listado de vértices
Auxiliar : w ϵ vertices
P1. visitado (v) <- verdadero
P2. ESCRIBIR (v)
P3. PARA cada vértice w adyacente a v HACER
		SI NOT visitado ( w ) ENTONCES
			dfs ( w )
P3. FIN
```

dfs ϵ O(a) con listas de adyacencia
dfs ϵ O(n2 ) con matriz de adyacencia

![[Pasted image 20240626093008.png]]

## En amplitud

El recorrido de amplitud de los vértices de un grafo tiene este funcionar:
- Comienza de un vértice V marcándolo como visitado, a partir de este vértice visita todos sus vértices adyacentes.
- luego visita todos los vértices adyacentes de los visitados.

Este algoritmo tiene una forma iterativa.

```
Algoritmo RecorridoEnAmplitud (G)
ENTRADA: G: GRAFO de vértices numerados
SALIDA: listado de vértices
Global: visitado: arreglo con dominio en vértices y valores bool
P1. PARA cada vértice v de G HACER
		visitado ( v ) <- falso
P2. PARA cada vértice v de G HACER
		SI NOT visitado ( v ) ENTONCES
			bfs ( v )
P3. FIN
```

```
ALGORITMO bfs (v)
ENTRADA: vértice v no visitado
SALIDA: listado de vértices
Auxiliar : q ∈ FILA(vertices), u,w ∈ vértices
P1. visitado (v) <- verdadero
P2. FILAVACIA (q)
P3. ENFILA(q,v)
P4. MIENTRAS NOT ESFILAVACIA(q) HACER
		u <- FRENTE(q)
		ESCRIBIR (u)
		DEFILA(q)
		PARA cada vértice w adyacente de u HACER
			SI NOT visitado(w) ENTONCES
				visitado(w) <- verdadero
				ENFILA(q,w)
P5. FIN
```

bfs ϵ O(a) con listas de adyacencia
bfs ϵ O(n2 ) con matriz de adyacencia

![[Pasted image 20240626094023.png]]

## Árbol de recubrimiento mínimo

Dado un grafo conexo, ponderado y no dirigido con costos no negativos, encontrar el árbol de recubrimiento mínimo de G con costo mínimo.
- Un árbol de recubrimiento mínimo es un subgrafo sin ciclos que contiene todos los vértices.
- Debe encontrar un conjunto de aristas que estén conectados todos los vértices y que el costo se al menor posible.
- Si el grafo es conexo al menos existe una solución. [[Grafos 3]]

![[Pasted image 20240626103417.png]]

![[Pasted image 20240626103430.png]]

Existe dos algoritmos reconocidos para resolver este problemas:
- Algoritmo de Prim
- Algoritmo de Kruskal (no lo veo en el cursado)

En ambos se aplica una estrategia Greedy.

## Algoritmo de Prim

Comienza por un vértice y en cada etapa elige un arco con menor costo que verifique que uno de sus vértices se encuentre en el
conjunto de vértices ya seleccionados y el otro afuera del conjunto.

Al incluir un nuevo arco a la solución, se agrega su otro extremo al
conjunto de vértices seleccionados.

```
ENTRADA: V: conjunto de vértices
E: conjunto de arcos de costo positivo
SALIDA: T: conjunto de arcos
AUXILIARES: B: conjunto de vértices
P1. B  { 1 } ; T=∅
P2. Mientras B≠V hacer
		Elegir en E un arco e=(v1,v2) de costo mínimo
			tal que v1∈B y v2∈V-B
		T <- T U {e}
		B <- B U {v2}
P3. Retorna T
P4. Fin.
```

![[Pasted image 20240626105603.png]]

El algoritmo de Prim es siempre de orden O(n2).
