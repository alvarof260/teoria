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
---
## INFORMACIÓN RELEVANTE:

---

- ✅ **Ideas más importantes del curso/clase:**
    - Tipos de complejidad de Notación O grande
    - RAM funcionamiento y características
    - Como determinar el crecimiento del costo en tiempo del algoritmo
- 📕 **El curso/clase en un párrafo o idea:**
- 📎 **Ligas/documentos y medios importantes:**

---

# ==REPASO==

## Tiempo de ejecución de un algoritmo

Sea ==T(n)== el tiempo de ejecución de un algoritmo para una entrada de tamaño n.

Se dice que ==T(n)== es ==O(f(n))== si existen dos constantes: c ==**(real)**== y n0 ==**(natural)**== tales que:

**==$T(n) ≤ c . f(n) cuando n ≥ n0$==**﻿

Cuando se dice que ==T(n)== es ==O(f(n))== se esta garantizando que la función ==f(n)== es una cota superior para el crecimiento de ==T(n).==

  

# ==Notación O grande==

Función es de complejidad notables:

- O(1) ==**_Complejidad constante_**==
- O(log n) ==_**Complejidad logarítmica**_==
- O(n) ==_**Complejidad lineal**_==
- O(n log n) ==_**Sin nombre**_==
- O(n elevado a 2) ==_**Complejidad cuadrática**_==
- O(n elevado a 3) ==_**Complejidad cubica**_==
- O(n elevado a x) ==_**Complejidad polinomial**_==
- O(2 elevado a n) ==**_Complejidad exponencial_**==
- O(c elevado a n) ==_**Complejidad exponencial con c ≥ 2**_==
- O(n!) ==**_Complejidad factorial_**==

==**_(esta lista se ordena de menor a mayor tiempo de ejecución de un algoritmo)_**==

# ==RAM (RANDOM ACCESS MACHINE)==

> ==Como medir el tiempo de ejecución en función del tamaño de la entrada de los datos del problema?==

**==RAM==** es un modelo que se usa para evaluar la complejidad de un ==**algoritmo**==.

Un modelo de maquina de acceso directo ==**RAM**== es una computadora teórica de un acumulador cuyas instrucciones no pueden modificarse a si mismas.

Consta de :

- Unidad de memoria 🎞️
- Unidad de entrada 🪵
- Procesador 🧠
- Unidad de salida 📦
- Conjunto de instrucciones 📝

Un programa ==**RAM**== es una secuencia finita de estas instrucciones.

![[2ca644c7-afd1-4b06-8103-539ac00dd259.png]]

En este modelo se supone que:

- La ==**entrada**== es una secuencia representada por una cinta de cuadrados en cada uno de los cuales esta almacenado un numero entero.
- Cuando un símbolo se lee de la cinta, la cabeza avanza al próximo cuadrado.
- La ==**salida**== es una cinta de cuadrados, que esta inicialmente en blanco, en cada uno de los cuales se puede escribir un entero.
- Cuando un símbolo se escribe en la cinta, la cabeza avanza al próximo cuadrado. Cuando ya se escribió un símbolo, no se puede cambiar.
- La ==**memoria**== es una sucesión (cantidad ilimitada) de registros ==**r0, r1, …**== , cada uno de los cuales puede almacenar un entero de tamaño arbitrario.
- Los cálculos se hacen en el primero de ellos, ==**r0**==, llamado ==**acumulador**==.
- El ==**programa**== es una secuencia de instrucciones.
- cada instrucción tiene un código de operación y una dirección.
- El ==**programa**== no se almacena en la ==**memoria**== y no se modifica a si mismo.
- El conjunto de instrucciones disponibles es similar al de las computadoras reales (operaciones aritméticas, de entrada salida, de bifurcación…)

![[adeabf45-2e97-44ca-a65a-29d5f02aaa7e.png]]

  

## ==Reglas Generales==

Para determinar el crecimiento del costo del ==**algoritmo**== en notación O grande, se van a analizar los distintos tipos de instrucciones:

- **Instrucciones que no se consideran**
- **Operaciones elementales**
- **Secuencia**
- **Selección**
- **Iteración**
- **Funciones no recursivas**
- **Funciones recursivas**

  

Se desprecia todo lo que no sea ejecutable por ejemplo los comentarios, declaraciones, tipificaciones, descripciones, etc.

### ==Operaciones elementales, O(1)==

- Leer un ==**valor**==.
- Escribir un ==**valor**== o ==**expresión simple**==.
- ==**Asignar**==, excepto de estructuras.
- Evaluar una expresión que no tenga invocación a una ==**función**==.
- Evaluar la condición de una ==**selección**== o ==**iteración**==.

### ==Secuencia==

- Hay que evaluar el tiempo de cada una de las instrucciones que componen la secuencia.
- El ==**tiempo de ejecución**== de toda la secuencia de instrucciones esta dado por la regla de la suma.
- Esto implica el mayor tiempo de ejecución de cada instrucción de la secuencia.

### ==Selección==

- Primero evaluar los tiempos que se necesitan para cada una de las distintas alternativas que podrían ejecutarse.
- Luego sumar el tiempo de evaluar la condición de ==**selección**==, mas el mas grande de los tiempos que se necesitan para cada una de las distintas alternativas.
- La condición de ==**selección**== en general es ==**O(1)**==**.**

### ==Iteración de un numero fijo de veces==

- Primero evaluar cada uno de los tiempos que necesitan cada una de las instrucciones que abarca el cuerpo de ==**iteración**==.
- Sumar el tiempo de todas las instrucciones que abarca la ==**iteración**== ==**_(el cuerpo)_**==, multiplicarlo por el numero total de ==**iteraciones**== que se efectúen.

### ==Iteración condicional==

- Primero evaluar cada uno de los tiempos que necesitan cada una de las instrucciones que abarca el cuerpo de la ==**iteración**==.
- Sumar el tiempo de todas las instrucciones que abarca la ==**iteración**== _==**(el cuerpo)**==_, mas el tiempo de evaluar la condición de terminación y todo multiplicarlo por el numero total de iteraciones que se efectúen.
- La condición de terminación es general es ==**O(1)**==.

### ==Funciones no recursivas==

- El tiempo de cada ==**función**== se debe evaluar por separado, comenzando por las ==**funciones**== que no invoquen a otras.
- Se evalúa el ==**tiempo de ejecución**== de la ==**función**== según las estructuras de control que tengan _**(secuencia, selección, iteración).**_
- Usando esos tiempos se evalúan las ==**funciones**== que las invocaron y así hasta llegar al ==**programa principal**== [[Técnicas Algorítmicas]].

### ==Funciones recursivas==

- Se asocia una ==**función**== de tiempo desconocida ==**T(n)**==.
- A continuación se plantea la recurrencia de ==**T(n)**== donde n mide el tamaño de la entrada.
- Luego se desarrolla la recurrencia, esto es una ecuación para ==**T(n)**== en términos de ==**T(k)**== para distintos valores de ==**k**==**.**

# ==EJEMPLOS==

![[504a7df7-99e5-471e-9953-6fb91e476211.png]]

![[/Untitled 13.png|Untitled 13.png]]

![[/Untitled 1 3.png|Untitled 1 3.png]]

![[/Untitled 2 3.png|Untitled 2 3.png]]

![[/Untitled 3 3.png|Untitled 3 3.png]]

![[/Untitled 4 2.png|Untitled 4 2.png]]

![[/Untitled 5 2.png|Untitled 5 2.png]]

![[/Untitled 6 2.png|Untitled 6 2.png]]

![[/Untitled 7 2.png|Untitled 7 2.png]]

![[/Untitled 8 2.png|Untitled 8 2.png]]