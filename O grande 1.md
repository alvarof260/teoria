---
Categoria:
  - Programacion
Ciclo: Módulo 3
Creado: Fecha inválida
Estado: Terminado
"Finalizado el:": Fecha inválida
Ligas/Documentos: https://www.youtube.com/watch?v=MyAiCtuhiqQ&ab_channel=ChioCode
Materia: Algoritmo y Estructura de Datos
Parcial: Parcial uno
Resumen: true
Tipo: 💻Curso o Clase
---
## INFORMACIÓN RELEVANTE:

---

- ✅ **Ideas más importantes del curso/clase:**
    - Notación O grande
    - Elección de un algoritmo
    - Rendimiento de un programa
- 📕 **El curso/clase en un párrafo o idea:**
    
    El curso se centra en la elección de algoritmos, el rendimiento de un programa y la eficiencia de los algoritmos. Se discute la elección entre un algoritmo simple y uno eficiente. Se analizan factores que afectan el rendimiento de un programa, como el tiempo de cálculo y los requisitos de almacenamiento. Se introduce la complejidad de espacio y tiempo de un programa. Finalmente, se discuten dos enfoques para el análisis de la eficiencia de los algoritmos: el enfoque experimental y el enfoque técnico.
    
- 📎 **Ligas/documentos y medios importantes:**
    
    [https://www.youtube.com/watch?v=MyAiCtuhiqQ&ab_channel=ChioCode](https://www.youtube.com/watch?v=MyAiCtuhiqQ&ab_channel=ChioCode)
    
    [https://www.youtube.com/watch?v=aR3UX2DjDXQ&ab_channel=hdeleon.net](https://www.youtube.com/watch?v=aR3UX2DjDXQ&ab_channel=hdeleon.net)
    

## RESUMEN DEL CLASE:

---

## ==ELECCIÓN DE UN ALGORITMO==

Cuando se requiere resolver un problema, se piensa en diferentes algoritmos, pero ==_¿base a que se elige?_== , depende la situación, si se busca eficacia o legibilidad, etc.

Dos metas contradictorias son:

- Un ==algoritmo== simple, fácil de entender, codificar y de rastrear errores.
- Un ==algoritmo== que haga uso eficiente de los recursos de la computadora.

casi siempre vas a tener que elegir entre estos dos objetivos, ya que si uno busca la legibilidad perderá eficiencia del algoritmo y viceversa también.

## ==RENDIMIENTO DE UN PROGRAMA==

Hay criterios para juzgar un programa que afectan directamente con la performance del mismo:

- ==Tiempo de calculo==
- ==Requisitos de almacenamiento==

### ==Definiciones==

- La ==complejidad de espacio== es la cantidad de memoria que necesita para realizar toda su ejecución.
- La ==complejidad de tiempo== es la cantidad de tiempo de computador que necesita para completar la ejecución.

Por lo tanto el análisis del rendimiento abarcara un análisis de estas dos mencionadas recientemente.

## ==COMPLEJIDAD DE ESPACIO DE UN PROGRAMA==

El espacio necesario para un programa es la suma de dos partes:

- ==PARTE FIJA==
- ==PARTE VARIABLE==

la ==parte fija==, que es independiente de las características de la entrada y salida del programa. Esta parte incluye el espacio para las instrucciones (el código), el espacio para variables simples y variables con componentes de tamaño fijo, espacio para constantes, etc.

La ==parte variable== que consiste del espacio necesario para variables con componentes cuyo tamaño depende de la instancia particular del problema que se esta resolviendo, espacio para variables dinámicas referenciadas y espacio para el stack de recursión.

## ==COMPLEJIDAD DE TIEMPO DE UN PROGRAMA==

El tiempo de un programa, es la suma del ==tiempo de compilación== y del ==tiempo de ejecución== de las instrucciones.

El ==tiempo de compilación== no depende de las características de la instancia, se supone una vez compilado se puede ejecutar varias veces sin recompilarlo al menos de que el código fuente sea modificado.

Por lo tanto lo mas significativo será el ==tiempo de ejecución==.

## ==Tiempo de ejecución de un programa==

Para dar una medida del tiempo de ejecución de un programa hay que analizar varios factores:

- La ==entrada== del programa, los datos de entrada, su tamaño.
- El ==algoritmo== aplicado.
- La calidad del código generado por el ==compilador== usado para crear la imagen objeto.
- La ==naturaleza y velocidad de las instrucciones== de maquina usadas para ejecutar el programa.

Se llama ==T(n)== al ==tiempo de ejecución== de un programa con una entrada de tamaño n. ==T(n)== es la llamada complejidad de tiempo de programa.

==T(n)== depende del ==algoritmo== usado. Se dice que el ==tiempo de ejecución== es proporcional a ==T(n====**)**==, la constante de proporcionalidad depende de la computadora.

==T(n)== es el número de instrucciones ejecutadas por el algoritmo en una computadora ideal por ejemplo la máquina RAM.

Principio de invariancia que afirma que dos implementaciones distintas de un mismo ==algoritmo== no diferirán en su eficiencia en mas de alguna constante multiplicativa. esto responde para la variantes en ==lenguaje== o ==maquina== que el ==algoritmo== es ejecutado.

## ==ANALISIS DEL TIEMPO DE EJECUCION DE UN PROGRAMA==

Para algunos programa el ==costo es uniforme== para distintas muestras de tamaño n. esto significa que el ==tiempo de ejecución== no varia para todas las entradas del mismo tamaño.

Para muchos programas el ==costo no es uniforme== para distintas muestra de tamaño n. esto significa que el ==tiempo de ejecución== de un ==algoritmo== varían para entradas del mismo tamaño.

![[/Untitled 16.png|Untitled 16.png]]

Cual elegir entre:

- ==T mejor (n)==
- ==T medio (n)==
- ==T peor (n)==

se debe definir ==T(n)== como el peor ==tiempo de ejecución==, ya que este es el máximo sobre todas las posibles muestras de tamaño n.

![[/Untitled 1 6.png|Untitled 1 6.png]]

![[/Untitled 2 5.png|Untitled 2 5.png]]

## ==EFICIENCIA DE ALGORITMOS==

Dos enfoques para el análisis de ==eficiencia de los algoritmos==:

- El ==enfoque experimental== _==(a posteriori)==_ consiste en programar todos los algoritmos y probarlos con diferentes instancias con ayuda de la computadora. Luego medir los ==tiempos de ejecución== [[O grande 2]].
- El ==enfoque técnico== ==_(a priori)_== consiste en determinar matemáticamente la cantidad de recursos ==_(tiempo de ejecución, espacio en memoria, etc.)_== necesarios para cada ==algoritmo== en función del tamaño de la instancia considerada.

Las ventajas del análisis teórico son:

lista

- No depende ni la computadora usada ni del ==lenguaje de programación==, ni siquiera las skills del programador.
- Ahorra el tiempo de programar ==algoritmos== ineficientes, así como el tiempo de maquina necesario para probarlos.
- Permite además estudiar la eficiencia de un ==algoritmo== cuando se estudia instancia de cualquier tamaño.
- El análisis requerido para estimar los recursos que usa un ==algoritmo== es un problema teórico y por ello se necesita un marco formal para su tratamiento.
- Se va a presentar una notación asintótica que permite comparar el orden de crecimiento de ==T(n)==, donde n es el tamaño de la entrada del ==algoritmo==.
- Por el ==principio de invarianza== se puede pensar ==T(n)== como el numero de instrucción en una computadora ideal.

![[/Untitled 3 5.png|Untitled 3 5.png]]

![[/Untitled 4 4.png|Untitled 4 4.png]]

![[/Untitled 5 4.png|Untitled 5 4.png]]

![[/Untitled 6 4.png|Untitled 6 4.png]]

![[/Untitled 7 4.png|Untitled 7 4.png]]

![[/Untitled 8 4.png|Untitled 8 4.png]]

![[/Untitled 9 3.png|Untitled 9 3.png]]

![[/Untitled 10 3.png|Untitled 10 3.png]]

![[/Untitled 11 3.png|Untitled 11 3.png]]

![[/Untitled 12 2.png|Untitled 12 2.png]]