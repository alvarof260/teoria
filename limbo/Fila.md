Una fila es una lista ordenada de cero o mas objetos de un mismo tipo que puede crecer por un extremo y decrecer por otro extremo. Estos se llaman **frente** y **final**.

Es una estructura de tipo **FIFO** *(first in, first out)*, las filas tienen un orden lineal.

![[Pasted image 20240612001209.png]]

>[!abstract] Sintaxis
>FILAVACIA : -> FILA
 ESFILAVACIA : FILA -> BOOL
 FRENTE : FILA -> ITEM U {indefinido}
 ENFILA : FILA X ITEM -> FILA
 DEFILA : FILA -> FILA
 LONGITUD : FILA -> entero ≥ 0
 PERTENECE : FILA x ITEM -> BOOL
 IGUALF : FILA x FILA -> BOOL
 CONCAT : FILA x FILA -> FILA
 INVERTIR : FILA -> FILA

>[!tip] Semantica
>Para todo q ∈ FILA , ∀ i ∈ ITEM
>
>ESFILAVACIA(FILAVACIA) ≡ TRUE
 ESFILAVACIA(ENFILA(q,i)) ≡ FALSE
 FRENTE(FILAVACIA) ≡ indefinido
 FRENTE(ENFILA(q,i)) ≡ si ESFILAVACIA(q) entonces i
 sino FRENTE(q)
 DEFILA(FILAVACIA) ≡ FILAVACIA
 DEFILA(ENFILA(q,i)) ≡ si ESFILAVACIA(q) entonces
 FILAVAVACIA
 sino ENFILA(DEFILA(q),i)
 LONGITUD ( FILAVACIA ) ≡ 0
 LONGITUD ( ENFILA(q,i) ) ≡ 1 + LONGITUD(q)
 PERTENECE (FILAVACIA,i) ≡ FALSO
 PERTENECE (ENFILA(q,i), j) ≡ i=j OR PERTENECE(q,j)
 IGUALF(FILAVACIA, FILAVACIA) ≡ TRUE
 IGUALF(FILAVACIA, ENFILA(f,i)) ≡ FALSE
 IGUALF(ENFILA(f,i), FILAVACIA) ≡ FALSE
 IGUALF(ENFILA(f,i), ENFILA(q,j)) ≡ i=j AND IGUALF(f,q)
 CONCAT(FILAVACIA,FILAVACIA) ≡ FILAVACIA
 CONCAT(ENFILA(q,j), FILAVACIA) ≡ ENFILA(q,j)
 CONCAT(FILAVACIA, ENFILA(p,i)) ≡ ENFILA (p,i)
 CONCAT(ENFILA(q,j), ENFILA(p,i)) ≡ ENFILA (CONCAT(ENFILA(q,j),p),i)
 INVERTIR (FILAVACIA) ≡ FILAVACIA
 INVERTIR(ENFILA(q,i)) ≡
 ENFILA(INVERTIR(DEFILA(ENFILA(q,i)), FRENTE(ENFILA(q,i))

Implementación:
- Arreglo
- Lista Enlazadas

## ADTS

Como usuario del ADT FILA, función recursiva

```
FUNCION LONGITUD (f) : FILA -> entero >= 0
	SI ESFILAVACIA(f) entonces
		RETORNA 0
	SINO
		RETORNA 1 + LONGITUD(DEFILA(f))
FIN
```

Como usuario del ADT FILA, función iterativa

```
FUNCION LONGITUD (f) : FILA -> entero >= 0
AUX: h ∈ entero
	h <- 0
	MIENTRAS NOT ESFILAVACIA(f) HACER
		h <- h + 1
		DEFILA(f)
	RETORNA h
FIN
```

Como usuario del ADT FILA, función recursiva

```
FUNCION PERTENECE (f,i) : FILA X ITEM -> bool
	SI ESFILAVACIA(f) entonces
		RETORNA FALSO
	SINO
		RETORNA FRENTE(F) = I OR PERTENECE(DEFILA(f), i)
FIN
```

Como usuario del ADT FILA, función iterativa

```
FUNCION PERTENECE (f, i) : FILA X ITEM -> bool
AUX: esta ∈ bool
	esta <- FALSO
	MIENTRAS NOT ESFILAVACIA(f) AND NOT esta HACER
		esta <- FRENTE(f) = i
		DEFILA(f)
	RETORNA esta
FIN
```

```
FUNCION PERTENECE (f, i) : FILA X ITEM -> bool
	MIENTRAS NOT ESFILAVACIA(f) AND NOT FRENTE(f) = i HACER
		DEFILA(f)
	RETORNA NOT ESFILAVACIA(f)
FIN
```

Como usuario del ADT FILA, función recursiva

```
FUNCION IGUALF (f1,f2) : FILA X FILA -> BOOL
	SI ESFILAVACIA(f1) AND ESFILAVACIA(f2) entonces
		Retorna TRUE
	SINO
		SI ESFILAVACIA(f1) OR ESFILAVACIA(f2) entonces
			RETORNA FALSE
		SINO
			Retorna FRENTE(f1)=FRENTE(f2) AND IGUALF(DEFILA(f1),DEFILA(f2))
FIN
```

Como usuario del ADT FILA, función iterativa

```
FUNCION IGUALF (f1,f2) : FILA X FILA -> BOOL
	MIENTRAS NOT ESFILAVACIA(f1) AND NOT ESFILAVACIA(f2) AND
    FRENTE(f1)=FRENTE(f2) hacer
		DEFILA(f1)
		DEFILA(f2)
	RETORNA ESFILAVACIA(f1) AND ESFILAVACIA(f2)
FIN
```

Como usuario del ADT FILA, función recursiva

```
FUNCION CONCAT (f1,f2) : FILA X FILA -> FILA
	SI ESFILAVACIA(f2) entonces
		RETORNA f1
	SINO
		ENFILA (f1, FRENTE(f2))
		DEFILA (f2)
		RETORNA CONCAT (f1,f2)
FIN
```

Como usuario del ADT FILA, función iterativa

```
FUNCION CONCAT (f1,f2) : FILA x FILA  FILA
	MIENTRAS NOT ESFILAVACIA(f2) hacer
		ENFILA(f1,FRENTE(f2))
		DEFILA(f2)
	RETORNA f1
FIN
```

Como usuario del ADT FILA, función recursiva

```
ALGORITMO INVERTIR (f,finv)
ENTRADA : f ∈ FILA
SALIDA: finv ∈ FILA, llega inicializada en FILAVACIA
AUXILIAR: itemaux ∈ ITEM

	SI NOT ESFILAVACIA(f) entonces
		itemaux  FRENTE(f)
		DEFILA(f)
		INVERTIR(f,finv)
		ENFILA(finv, itemaux)
FIN
```

Como usuario del ADT FILA, funcion iterativa

```
ALGORITMO INVERTIR(f,finv)
ENTRADA : f ∈ FILA
SALIDA: finv ∈ FILA
AUXILIAR: pilaux ∈ PILA(ITEM)

	PILAVACIA(pilaux)
	MIENTRAS NOT ESFILAVACIA(f) hacer
		PUSH (pilaux, FRENTE(f))
		DEFILA(f)
	FILAVACIA(finv)
	MIENTRAS NOT ESPILAVACIA(pilaux) HACER
		ENFILA(finv, TOP(pilaux))
		POP(pilaux)
FIN
```