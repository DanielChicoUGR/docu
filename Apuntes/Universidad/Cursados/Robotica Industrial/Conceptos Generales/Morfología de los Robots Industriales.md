```ad-quote
title:Definición
**Cadena Cinemática**::Conjunto de eslabones y articulaciones conectados entre sí para permitir el movimiento de un robot. Cada eslabón representa un cuerpo rígido del robot y cada artucylación representa la conexión entre dos eslabones, lo que permite el movimiento relativo entre ellos.
```

```ad-quote
title:Definición
**Robot Manipulador**::es un robot formado por una serie de elementos estructurales sólidos y rígidos unidos mediante **articulaciones**
```

La mayor parte de los robots industriales son brazos articulados
Generalmente constituyen una cadena cinemática abierta
	Cada eslabón está conectado (mediante una articulación) exclusivamente al enlace anterior.
	Un extremo de la cadena es fijo (==base==) y el otro es libre (==efector==)
Las articulaciones y eslabones se enumeran desde la ==base hacia afuera==
<!--SR:!2023-05-09,1,210!2023-05-09,1,210!2023-05-09,1,220-->

```ad-example
title: Ejemplo de robot Manipulador
![[Pasted image 20230421125822.png]]


![[Pasted image 20230421130449.png]]
```
La construcción física de la mayor aprte de los robots industriales se asemeja a la anatomía del brazo humano
# Tipos De Aritculaciones:
![[Articulaciones]]
# Grados De Libertad
```ad-quote
title:Definición
**Grado de libertad**::Cada movimiento indepenndiente que puede hecer el robot en la unión de dos eslabones
```
El número de los grados de libertad del robot viene determinado por la ==suma de los grados de libertad== de cada una de las articulaciones.
<!--SR:!2023-05-11,3,250-->

```ad-important
Para articulaciones con mas de dos grados de libertad, se dividen en tantas articulaciones como grados de livertad tenga la articulacione original, todas ellas unidas por un eslabón de longitud 0
```

**Núm. de GDL=Núm. de articulaciones** siempre y cuando:
?
- El robot constituye una cadena cinemática abierta
- Las articulaciones son de tipo rotación o prismática
<!--SR:!2023-05-10,3,250-->

En general, el número de grados de libertad de una cadena cinemática (abierta o cerrada) puede ser obtenido mediante la fórmula de Grübler: $NGDL=\lambda * (n-j-1)+ \sum_{i=1}^{j}f_i$ donde:
	1. $\lambda \rightarrow$ GDL del espacio de trabajo (3 en el plano, 6 en el espacio)
	2. n $\rightarrow$ Número de eslabines (incluyendo la base)
	3. j $\rightarrow$ Número de articulaciones
	4. $f_i \rightarrow$ Grados de libertad de la i-ésima articulación

Para posicionar y orientar un cuerpo de cualquier manera en el espacio son necesarios 6 parámetros:
?
- 3 para la posición
- 3 para orientar
<!--SR:!2023-05-10,2,230-->

Para posicionar y orientar un efector de un robot en cualquier punto en el espacio serán necesarios al menos ==6 GDL== 
	< 6 GDL $\rightarrow$ Menor espacio de trabajo o capacidad de orientación
	> 6 GDL $\rightarrow$ Posibilidad de esquivar objetos.
Para describir el estado de un robot decesitaremos ==una variable de posición independiente por cada GDL==.
<!--SR:!2023-05-09,1,210!2023-05-10,3,250-->

Un mayor numero de grados de libertad aumenta la maniobravilidad pero complica el control.

# Efector
La elección del efector se realiza de acuerdo a la tarea que va a realizar el robot
Se pueden clasificar en:
- Pinzas
- Herramientas $\rightarrow$ Soplete, atornillador, ventanilla, pistola de pintura, cañon de agua

Los elementos de sujección pueden ser:
- De tipo mecánico $\rightarrow$ ventosas, adesivos, ganchos...
- De accionamiento hidraúlico o eléctrico

![[Pasted image 20230421191034.png]]

Se denomina ==Punto de centro de Herramienta (TCP)== al punto focal de la pinza o herramienta
<!--SR:!2023-05-09,1,210-->

![[Pasted image 20230421191104.png]]
