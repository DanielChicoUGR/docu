El proceso presentado en la nota [[Jacobiana geométrica]] no es el más adecuado para implementarlo en un computador debido al uso intenso de derivadas.

Alternativamente se puede usar un procedimiento numérico basado en las matrices de transformación homogénea $^{i-1}T_i$ 

Este procedimiento calcula por separado la i-ésima columna de la jacobiana geométrica, $J_i$, como:
?
- Si la i-ésima articulación es de giro: $J_i=\begin{bmatrix} ^0z_{i-1}\times^{i-1}p_n \\ ^0z_{i-1} \end{bmatrix}$ 
	- EL $\times$ Significa producto vectorial de las dos columnas
- Si la i-ésima articulación es de desplazamiento : $J_i=\begin{bmatrix} ^0z_{i-1} \\ 0_{3\times1}\end{bmatrix}$ 
- donde :
	- $^0z_i=^0T_i(1:3,3)$ (las 3 primeras filas de la 3 columna, como slice en python)
	- $^ip_n=^0T_n(1:3,4) - ^0T_i(1:3,4)$ 
- La jacobiana se obtiene concatenando todas las columnas.


### Ejemplo Scara

![[Pasted image 20230531174506.png]]
![[Pasted image 20230531174517.png]]
![[Pasted image 20230531174530.png]]
![[Pasted image 20230531174540.png]]
![[Pasted image 20230531174552.png]]
![[Pasted image 20230531174606.png]]

