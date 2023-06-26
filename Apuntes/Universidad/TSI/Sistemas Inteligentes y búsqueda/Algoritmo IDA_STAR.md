### Definición:
?
-  Combina el [[Algoritmo A_STAR]] con el [[Algoritmo de búsqueda con Profundidad Iterativa]]
- El límite lo establece la función de evaluación
	- En cada iteración, el límite es el menor de los valores devuelto por la función de evaluación de los nodos que excedieron el límite en la iteración anterior.


### Características:

**Completo**-> Si existe solución la encuentra

**Óptimo** -> Con las mismas características que el [[Algoritmo A_STAR]]

**Complejidad temporal** $\rightarrow$ Exponencial 

**Complejidad espacial** $\rightarrow$ Lineal

### Algoritmo
```pseudo
\begin{algorithm} 
\caption{IDA*} 
\begin{algorithmic} 
\Function{Busqueda-IDA*}{$problema$}
    \State nodo-raiz $\gets$ CREAR-NODO-RAIZ(problema)
    \State limite $\gets$ nodo-raiz.HEURISTICA
    \Repeat
		\State resultado $\gets$ BUSQUEDA-A*-ITERATIVA(problema,nodo-raiz,limite)
		\If{resultado=solucion} \Comment{sea una solución valida}
			\Return solución
		\EndIf
		\If{resultado=$\infty$} \Comment{No se encuentra la solución}
			\Return fallo
		\EndIf
		\State limite $\gets$ resultado
	\Until{$\infty$} \Comment{Repetir indefinidamente}
\EndFunction
\end{algorithmic}
\end{algorithm}


\begin{algorithm} 
\caption{IDA\_2*} 
\begin{algorithmic} 
\Function{BUSQUEDA-A*-ITERATIVA}{problema,nodo-raiz,limite}
    \If{nodo.VALOR > límite}
		\Return nodo.VALOR
	\EndIf

	\If{problema.ES-OBJETIVO(nodo)}
		\Return nodo
	\EndIf
	\State minimo $\gets \infty$
	\For{accion in problema.ACCIONES(nodo.ESTADO)}
		\State hijo $\gets$ CREAR-NODO-HIJO(problema,nodo,accion)
		\State resultado $\gets$ BÚSQUEDA-A*-ITERATIVA(problema,hijo,límite)
		\If{resultado = solucion}
			\Return solucion
		\EndIf
		\If{resultado<minimo}
			\State minimo $\gets$ resultado
		\EndIf
	\EndFor
	\Return minimo
\EndFunction


\end{algorithmic} 

\end{algorithm}
```

### Análisis:

#### Ventajas:
1. Las mismas que el [[Algoritmo A_STAR]]
2. Ocupa muy poco espacio en memoria

#### Desventajas:
1. Complejidad en tiempo exponencial
2. Maneja mal los numero decimales???? WTF
3. Se expanden muchas veces los mismos nodos -> Problema