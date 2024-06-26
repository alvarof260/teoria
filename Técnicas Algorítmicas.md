---
Categoria:
  - Programacion
Ciclo: Módulo 3
Creado: Fecha inválida
Estado: Terminado
"Finalizado el:": Fecha inválida
Materia: Algoritmo y Estructura de Datos
Parcial: Parcial uno
Resumen: true
Tipo: 💻Curso o Clase
tags:
---
## INFORMACIÓN RELEVANTE:

---

- ✅ **Ideas más importantes del curso/clase:**
- 📕 **El curso/clase en un párrafo o idea:**
    
    El curso de Técnicas Algorítmicas aborda varios conceptos clave. La recursión, aunque a menudo puede ser reemplazada por algoritmos iterativos, se destaca por su legibilidad y eficiencia dependiendo del manejo de la pila de recursión. La metodología Divide & Conquer, que resuelve problemas de manera descendente, a menudo utiliza la recursión en sus implementaciones. La búsqueda binaria se utiliza para determinar la pertenencia y encontrar la posición de un valor en un arreglo ordenado. La programación dinámica, una técnica ascendente, comienza con los casos más pequeños y combina soluciones para resolver problemas de optimización y grafos.
    
- 📎 **Ligas/documentos y medios importantes:**

## RESUMEN DEL CURSO:

---

## ==Recursión==

Planteos que se hacen con esta técnica son si un **==algoritmo recursivo==** se puede ser reemplazado por un **==algoritmo iterativo==** que haga lo mismo y la respuesta suele ser afirmativa.

La diferencia entre un **==algoritmo recursivo==** y uno **==iterativo==** es la **==legibilidad==**; los primeros suelen ser mas legibles que los segundos. También, se pone en duda la **==eficiencia de la técnica de recursión==** pero, la cual es ==**muy eficiente en términos algorítmicos**==, pero depende del manejo adecuado de la ==**pila de recursión en los lenguajes de programación**==.

## ==Divide & Conquer==

Es una ==**metodología top-down**== ya que resuelven los problemas de una manera descendente en 2 etapas:

- ==Divide: división en problemas mas chicos que se resuelven independientemente==
- ==Conquer: la solución original se resuelven con la combinación de las soluciones de los pequeños problemas.==

Generalmente se usa la ==**recursión**== en las implementaciones de estos algoritmo, aunque también se puede aplicar ==**iterativa**==.

![[/Untitled 15.png|Untitled 15.png]]

![[/Untitled 1 5.png|Untitled 1 5.png]]

![[/Untitled 2 4.png|Untitled 2 4.png]]

## ==Búsqueda Binaria==

Dado un arreglo A[1,… ,n] buscar un dado x por el método de búsqueda binaria

La ==**búsqueda binaria**==, determina la pertenencia y encuentra la posición de un dado valor en un arreglo ordenado.

Durante el proceso compara el valor con el elemento x en la posición del medio del arreglo

- ==Si x coincide con el elemento del medio: lo encontró.==
- ==Si x es menor que el del medio: continua con la parte izquierda del arreglo.==
- ==Si x es mayor que el del medio: continua con la mitad derecha.==
- ==Asi sigue hasta que lo encuentre o se crucen los indices==

## ==Algoritmo iterativo==

![[/Untitled 3 4.png|Untitled 3 4.png]]

![[/Untitled 4 3.png|Untitled 4 3.png]]

![[/Untitled 5 3.png|Untitled 5 3.png]]

## ==Algoritmo Recursivo==

![[/Untitled 6 3.png|Untitled 6 3.png]]

  

Tiempo de ejecución: ==**T(n) = a T(n/b) + c n elevado a k**==

Teorema: la solución de la ecuación:

$T(n)=aT(n/b)+cn^k$﻿

**==donde c ≥ 0 real, a ≥ 1 real, b≥2 entero y k≥0 entero,==**

es:

- ==T(n) = O (n logba ) si a > bk==
- ==T(n) = O ( nk logb n) si a = bk==
- ==T(n) = O ( nk ) si a < bk==

Para estimar el tiempo de ejecución de búsqueda binaria:

==**a=1, b=2, k=0 entonces: a = b elevado a k**==

la solución de la ecuación segunda el teorema es entonces:

==**T(n) = O(n elevado a k log b n)**==

→ T(n) ϵ O ( log2 n) para la búsqueda binaria

## ==Programación Dinámica==

- ==Es una técnica ascendente (bottom up)==
- ==Comienza con los casos mas pequeños==
- ==Combinando las soluciones, y así obtiene las soluciones para casos mayores, hasta que llega a la solución del problema original.==
- ==Forma una tabla de resultados de subproblemas para alcanzar la solución por lo tanto no recalcula==
- ==Se utiliza para la resolución de problemas de optimización==
- ==Se utiliza para los grafos==

![[/Untitled 7 3.png|Untitled 7 3.png]]

![[/Untitled 8 3.png|Untitled 8 3.png]]

![[/Untitled 9 2.png|Untitled 9 2.png]]

![[/Untitled 10 2.png|Untitled 10 2.png]]

![[/Untitled 11 2.png|Untitled 11 2.png]]