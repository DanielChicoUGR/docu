### Definición:
?
- Similar al [[Algoritmo A_STAR]] con la diferencia de que el tamaño de abiertos esta fijo, cuando este se llena elimina el peor nodo en el (Puede joder la busqueda)
- Al eliminar nodos, en el padre se almacena el valor del hijo para regenerarlo si el resto d e caminos son peores

### Características:

**Completo**-> Si, siempre que se pueda alcanzar una solución con la memoria disponible

**Óptimo** -> Si, como el caso anterior, sino la mejor solución encontrada

**Complejidad temporal** $\rightarrow$ exponencial 

**Complejidad espacial** $\rightarrow$ constante dependiente de la memoria

### Algoritmo
```pseudo
\begin{algorithm} 
\caption{A\_Star} 
\begin{algorithmic} 
\Function{SMA*}{$inicio, destino, heuristica$}
    \State $frontera \gets$ priority queue \Comment{Tamaño máximo fijo desde este momento}
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

### Análisis:

#### Ventajas:
1. Las mismas que [[Algoritmo A_STAR]]
2. Uso óptimo del espacio
3. No expande muchas veces los mismos nodos

#### Desventajas:
1. Obtener la solución y que sea óptima depende de si se puede alcanzar con la memoria disponible