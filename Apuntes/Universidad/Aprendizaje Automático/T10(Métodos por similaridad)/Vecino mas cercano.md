## Elementos Necesarios:
?
- Dataset para training ($X$) etiquetado con su correspondiente funcion $f$ (desconocida)
- Función de distancia/similitud entre items del dataset: $d(x,y): \mathbb{R}^{k} \times \mathbb{R}^{k} \rightarrow \mathbb{R}$ 

## Clasificador 1-NN
```pseudo
\begin{algorithm} 
\caption{Clasificador 1-NN} 
\begin{algorithmic} 
\Function{Alg}{$data$}
    \State Almacena Datos entrenamiento
    \For{ Cada nuevo dato}
		\State Buscar en los datos almacenados el mas cercano
		\State Asignar la etiqueta del punto mas cercano
	\EndFor
\EndFunction
\end{algorithmic} 
\end{algorithm}
```

## Pros:
?
- No se necesita aprender una función, se almacenan los datos
- Técnica de clasificación binaria ultrasencilla
- Funciona bastante bién en la práctica

## Contras
?
- El error depende de la distribución de los datos del dataset
- Compromiso desconocido entre la distancia y la dimension del vector de características (Su simplicidad es negativa en este sentido)

### Representación geométrica de la hipótesis devuelta para un dataset en 2D
![[Screenshot_2023-07-07-20-13-30-452_md.obsidian.png]] El Algoritmo 1-NN siempre devuelve un mapa de Voronoid de los puntos del dataset.

## Dimensión VC

*Dimensión VC del método*:: $\infty$ 
Por qué? -> Al poder memorizar cualquier cantidad de puntos (a priori), su función de crecimiento tiende a infinito y por tanto su dimensión VC también.


### Como estimar el error?
Modificando La regla de bayes
