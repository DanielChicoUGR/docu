El objetivo es aprender una funcion desconocida $f$ con:
	1. Muestras de datos
	2. El valor de la función para cada uno de los datos (etiqueta)
**Asume**:
	1. La unica información disponible es la de la muestra
	2. Se puede aproximar a $f$ a travesd e algún criterio de aprendizaje
	**Objetivo**:: Encontrar una función $g$ que aproxime a $f$ no solo para el dattaset de entreno sino para toda la población

```mermaid
flowchart 
p1[1. Población desconocida]
p2[2. Muestras S +Etiquetas L ]
p3[3. Programa de aprendizaje]
p4[4. $F:S \rightarrow L$ función aprendida]
p31[3.1 Clase de funciones $H$]
p32[3.2 Algoritmo de oprimización]
p1--> p2-->p3-->p4
p31 & p32-->p3

```
## Formalización:
![[Pasted image 20230419125947.png]]
