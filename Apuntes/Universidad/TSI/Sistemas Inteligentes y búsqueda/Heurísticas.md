## Heurística y tipos de problemas

**Heurística**::Criterios, métodos o principios para decidir cuál de entre varias acciones promete ser la mejor para alcanzar una determinada meta

## Propiedades de los métodos heurísticos:

Muchos métodos heurísticos no tiene garantías excepto aquellos de primero el mejor. Para que un problema sea resoluble por métodos heurísticos debe tener las siguientes propiedades (**el problema**):
1. El espacio de estados del problema debe poderse representar como un **[[grafo localmente finito]]**.
2. El coste de ir de un nodo a cualquiera de sus descendientes es siempre mayor que 0. $C(N_i,N_j)>0 \ \forall N_i \ \forall N_j \in \text{sucesores}(N_i)$

### Notación:
![[Notación heurísticas]]

### Propiedades de $f^*$:
1. $f^*(N)=C^*$ $\forall N \in P^*_{S-\Gamma'}$ , la suma de $h^*$ y $g^*$ es el coste óptimo si N forma parte de un camino óptimo del nodo inicio al nodo objetivo.
2. 