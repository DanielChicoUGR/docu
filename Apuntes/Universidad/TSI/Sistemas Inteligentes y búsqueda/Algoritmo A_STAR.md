### Definición:
?
1. Método mas conocido de búsqueda por el mejor nodo
2. La idea es evitar explorar caminos que ya sabemos que no son interesantes por su costo
3. La función de evaluación es $f(n)=g(n)+h(n) \rightarrow A^*$ 
	- $g(n) \rightarrow$ costo actual del camino
	- $h(n) \rightarrow$ costo heurístico del camino
	- $f(n) \rightarrow$ costo total estimado de pasar por ese nodo
4. Intenta expandir el nodo con mejor función de evaluación

### Características:

**Completo**-> Encuentra solución <-> El grafo es localmente finito y h sea monótona
	Todos los nodos tienen un numero finito de hijos.

**Óptimo** -> Siempre y cuando h sea admisible encuentra la solución óptima

**Complejidad temporal** $\rightarrow O(b^d)$ 

**Complejidad espacial** Exponencial

### Algoritmo
```pseudo
\begin{algorithm} 
\caption{A\_Star} 
\begin{algorithmic} 
\Function{A*}{$inicio, destino, heuristica$}
    \State $frontera \gets$ priority queue
    \State $frontera.push((inicio, 0))$
    \State $costo\_acumulado \gets$ map
    \State $costo\_acumulado[inicio] \gets 0$
    \State $padres \gets$ map
    \While{$frontera$ is not empty}
        \State $actual \gets frontera.top().first$
        \If{$actual = destino$}
            \State \Return reconstruir\_camino(padres, inicio, destino)
        \EndIf
        \State $frontera.pop()$
        \For{$vecino$ \textbf{in} vecinos(actual)}
            \State $nuevo\_costo \gets costo\_acumulado[actual] + costo(actual, vecino)$
            \If{$vecino$ not in $costo\_acumulado$ or $nuevo\_costo < costo\_acumulado[vecino]$}
                \State $costo\_acumulado[vecino] \gets nuevo\_costo$
                \State $prioridad \gets nuevo\_costo + heuristica(vecino, destino)$
                \State $frontera.push((vecino, prioridad))$
                \State $padres[vecino] \gets actual$
            \EndIf
        \EndFor
    \EndWhile
    \State \Return failure
\EndFunction


\end{algorithmic} 
\end{algorithm}
```

- El algoritmo posee una lista de nodos ABIERTOS, donde al principio está el nodo inicial.
- Existe otra lista, CERRADOS, que está vacío.  
- Comienza un bucle que se repite hasta encontrar solución o hasta que ABIERTOS está vacío. 
	- Seleccionar el mejor nodo de ABIERTO. 
	- Si es el nodo objetivo terminar. 
	- En caso contrario, expandir ese nodo. 
	- Para cada uno de sus sucesores: 
		- Si está en ABIERTOS, insertarlo manteniendo la información del mejor padre.
		- Si está en CERRADOS, insertarlo manteniendo la información del mejor padre y actualizar la información de los descendientes. 
		- En otro caso insertarlo como un nodo nuevo

### Análisis:

#### Ventajas:
1. Admite costes variables de acciones
2. Evita caminos inútiles
3. Reduce su complejidad con una buena heurística
4. Es completo y óptimo de manera eficiente

#### Desventajas:
1. Complejidad espacial y temporal exponenicial.