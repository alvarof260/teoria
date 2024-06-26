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
## INFORMACION RELEVANTE:

---

- ✅ **Ideas más importantes del curso/clase:**
- 📕 **El curso/clase en un párrafo o idea:**
- 📎 **Ligas/documentos y medios importantes:**

## RESUMEN DEL CLASE:

---

# ==**Algoritmos**==

> ==_“Un algoritmo hay que verlo para creerlo”_== ==por== ==**Donald Knuth**==

> ==_“Algoritmo + Estructura de Datos = Programas”_== por **Niklaus Wirth**

> ==_“Algoritmos: un lenguaje común para la naturaleza, los humanos y la computadora.”_== ==por== **==Avi Wigderson==**

# ==**Estructura de Datos**==

> ==_“De hecho, afirmaré que la diferencia entre un mal programador y uno bueno es si considera más importante su código o sus estructuras de datos. Los malos programadores se preocupan por el código. Los buenos programadores se preocupan por las estructuras de datos y sus relaciones.”_== por **Linus Torvalds**

> ==_“Diseña tus estructuras de datos primero, y el resto del programa se escribirá solo.”_== por **David Jones**

# ==¿Por qué estudiar algoritmos?==

- Por su amplio impacto y posibilidades actuales y futuras.
- Sus antiguas raíces y nuevas oportunidades de aplicación.
- Para resolver problemas que no podrían resolverse de otra manera.
- Para ser un programador competente.
- Para entretenerse.
- Para obtener ganancias.

# ==Significado de Algoritmo==

- ==**Algoritmo**==. Conjunto ordenado y finito de operaciones que permite hallar la solución de un problema.
- ==**Algorítmico**==. Perteneciente o relativo algoritmo.
- ==**Algoritmia**==. Ciencia que estudia los algoritmos.

concepto moderno de Algoritmo:

- Proceso
- Método
- Receta
- Técnica
- Procedimiento
- Rutina
- Método de calculo

En Informática el concepto de algoritmo esta asociado a algo mas riguroso que a una secuencia de operaciones.

# ==Definición de Algoritmo==

Un algoritmo es una secuencia finita de instrucciones a ejecutar sobre automata para resolver un problema en un tiempo finito.

## ==Condiciones:==

- ==**Entrada:**== puede ser vacía.
- ==**Salida:**== no puede ser vacía.
- ==**Definido:**== cada instrucción debe definirse de modo preciso, sin ambigüedades, claras y rigurosa.
- ==**Finito:**== el algoritmo debe terminar en un numero finito de pasos.
- ==**Determinístico:**== siempre la misma salida para idénticas entradas.

## ==Características:==

- Correcto
- Simple
- Elegante
- Eficiente 
- Adaptable

## ==**Algoritmo de Euclides**==

```JavaScript
ENTRADA: m, n dos numeros enteros positivos
SALIDA: m, entero positivo MCD de m y n
Auxiliar: r, entero positivo o nulo

E1. Leer(m,n)
E2. Mientras n!= 0 Hacer
				r <- resto(m/n)
				m <- n
				n <- r
E3. Escribir(m)
E4. Fin
```

## ==Problema de Multiplicación==

Problema:

Multiplicar dos enteros positivos a y b.

Este problema se puede resolver con varios algoritmos:

- Multiplicación clásica
- Multiplicación sumas sucesivas
- Multiplicación en bloque
- Multiplicación hindú o Fibonacci
- Multiplicación a la rusa
- Multiplicación egipcia
- Multiplicación D&C

> [!important]  
> Cual algoritmo es mejor?  

- ==**Multiplicación clásica**==
    
    Ej. a=981, b=12
    
    Para calcular 981x12 se multiplica cifra por cifra y suma:
    
    **==a==** tiene m cifras
    
    ==**b**== tiene n cifras
    
    ```JavaScript
      981
     x 12
     -----
     1962
      981
     -----
     11772
    ```
    
    total de operaciones = m x n multiplicaciones + 1 suma
    
- ==**Multiplicación sumas sucesivas**==
    
    1. Sumar b veces el numero a:
        
        ==**a x b = a + a + … + a**== (b veces)
        
    
    total de operaciones = b sumas
    
    Ej. a=981, b=12
    
    981 x 12 = 981+981+…+981===**11772**==
    
    2. Sumar a veces el numero b:
    
    ==**a x b = b + b+ … + b**== (a veces)
    
    total de operaciones = a sumas
    
    Ej. a=981, b=12
    
    981 x 12 = 12+12+…+12===**11772**==
    
      
    
- ==**Multiplicación en bloque**==
    
    ![[/Untitled 12.png|Untitled 12.png]]
    
- **==Multiplicación hindú o de Fibonacci==**
    
    ![[/Untitled 1 2.png|Untitled 1 2.png]]
    
- ==Multiplicación a la rusa==
    
    ![[/Untitled 2 2.png|Untitled 2 2.png]]
    
- ==Multiplicación egipcia==
    
    ![[/Untitled 3 2.png|Untitled 3 2.png]]
    

Las operaciones binarias es mas eficiente por que para el hardware es el mas cercano. [[O grande 1]]