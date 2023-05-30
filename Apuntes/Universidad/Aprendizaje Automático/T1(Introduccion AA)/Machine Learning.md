**Definición**:: Un programa aprende de una experiencia $E$ con respecto a una clase de tareas $T$ con un desempeño $P$ <-> Al aumentar la cantidad de experiencias $E$, $P_T$ también aumenta
	Cuantos mas datos tengamos, mayor experiencia.
# Paradigmas
## [[Aprendizaje Supervisado]]
Aprende una función objetivo con:
	1. Una muestra de datos
	2. Una etiqueta para cada datos de la muestra.
## [[Aprendizaje No Supervisado]]
Aprende propiedades de los datos obtenidos, los intenta aglomerar en distintos clusteres en función de los datos. Una menor dimensionalidad de los datos suele indicar que se ha encontrado información
### Aprendizaje Autosupervisado
Transforma los datos observados en otros (normalmente mas utiles para ese caso de uso) resolviendo "Tareas de pretexto" (tareas que si son supervisadas).

## Transferencia de conocimiento
Como se trasmiten datos entre distintas tareas

## Aprendizaje Reforzado
Compuesto por datos y recompensas a la predicción. Se obtiene una política de actualización e intenta maximizar las recompensas.