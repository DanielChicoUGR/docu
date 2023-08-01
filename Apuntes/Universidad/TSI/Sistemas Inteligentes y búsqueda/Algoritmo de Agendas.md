
Es una generalización del algoritmo A*, aunque surgió como un algoritmo propio de teoría de números.


# Características:
?
1. El algoritmo explora tareas no estados, el algoritmo realiza una tarea:
	1. Una tarea consiste en una descripción de la misma , una lista de justificaciones (los padres del nodo, el como se llega a ese estado) y una valoración heurística
	2. Una vez se realiza la tarea (similar a expandir un nodo), surgén nuevas tareas que ha de gestionar (de ahí la idea de agenda)
	3. La agenda es una lista de tareas, de donde se quiere realizar la tarea mas importante. Esto es equivalente a explorar el nodo mas prometedos de Abiertos.
	4. No existe como tal un conjunto de Cerrados pero se puede entender como una tarea realizada
	5. El algoritmo toma una tarea de la agenda, luego de realizarla obtiene otra tarea, la cual puede que ya exista en la agenda pero con otro padre/justificación

Formalmente este algoritmo es muy similar al de A\*, *aunque este algoritmo no esta destinado a encontrar el camino mas corto*, A\* se puede entender como una particularización de este.

Este algoritmo, al realizar una tarea, almacena su predecesor junto a esta, para un estado cualquiera se almacenan todos los padres, en A* existe un operador que discrimina los peores padres.
