
## Lenguaje recursivamente enumerable

>[!def]
Un lenguaje $L ⊆ A^∗$ se dice recursivamente enumerable (e.r.) si y solo si existe una máquina de Turing $M = (Q,A,C,δ,q0,\#,F)$ tal que $L(M) = L$.


## Lenguaje Recursivo:

>[!def]
Un lenguaje se dice recursivo si es aceptado por una MT que siempre termina: todas las palabras son aceptadas o rechazadas

Un lenguaje recursivo es siempre recursivamente enumerable. Los lenguajes recursivos son aquellos cuyo problema de aceptación pueder ser resuelto mediante un algoritmo. En el caso de lenguajes recursivos, podemos suponer que hay dos tipos de estados finales: de aceptación y de rechazo. La máquina acepta cuando se llega a un estado de aceptación y rechaza cuando llega a un estado de rechazo.

## Problemas de búsqueda

Son los problemas genéricos cuando $F(x)$ puede ser vacío o contener varios elementos: Para una entrada x el problema consiste en encontrar una solución y que cumpla una relación con x cuando este exista y decir `NO` cuando $F(x) = \emptyset$

## Problemas de Decisión: 

Son aquellos en los que las soluciones son $Y = {SI,NO}$ y cada entrada x tiene una única solución. Ejemplo: dado un grafo determinar si tiene un circuito hamiltoniano.

Los probemas de decisión son especialmente importantes ya que son simples y es fácil razonar sobre ellos y además cualquier otro problema tiene asociado un problema de decisión

### Problemas de umbral para problemas de optimización: 

Los mismos datos de un problema de optimización más un umbral K y ahora se pregunta si existe una solución de valor mayor o menor que el valor K según sea un problema de máximo o mínimo. Ejemplo: dado un caso del problema del viajante de comercio y un valor K determinar si existe un circuito de coste menor o igual que K. 

### Problemas de existencia para problemas de búsqueda: 

Dado un x, determinar si existe un y tal que sea una solución de x. 

### Problemas de comprobación para problemas de función y búsqueda: 

Dado x y una posible solución y determinar si y es una solución de x.

## Problemas de Optimización: 

La solución optimiza (minimiza o maximiza) una función definida sobre un conjunto de soluciones factibles asociadas a la entrada. Ejemplo: el problema del viajante de comercio. 

## Problemas de función: 

Cada entrada x tiene siembre una y sólo una solución: $F(x)$ tiene un solo elemento. Por ejemplo, dado un número n calcular su cuadrado $n^2$