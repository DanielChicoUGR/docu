![[Pasted image 20230530181007.png]]
**Modelo Cinemático Directo**::Relaciona las variables de las articulaciones con la posición del efector
	- $$x=f_x(q_1,\dots,q_n,l_1,\dots,l_n)$$
	- $$y=f_y(q_1,\dots,q_n,l_1,\dots,l_n)$$
	- $$z=f_z(q_1,\dots,q_n,l_1,\dots,l_n)$$
	- $$\alpha=f_\alpha(q_1,\dots,q_n,l_1,\dots,l_n)$$
	- $$\beta=f_\beta(q_1,\dots,q_n,l_1,\dots,l_n)$$
	- $$\gamma=f_\gamma(q_1,\dots,q_n,l_1,\dots,l_n)$$
**Modelo Cinemático Inverso**::Relaciona la posición del efector con las variables de articulación
	- $$q_1=f_{q1}(x,y,z,\alpha,\beta,\gamma,l_1,\dots,l_n)$$
	- $$q_2=f_{q2}(x,y,z,\alpha,\beta,\gamma,l_1,\dots,l_n)$$
	- $$q_n=f_{qn}(x,y,z,\alpha,\beta,\gamma,l_1,\dots,l_n)$$
	- 

# Modelo Cinemático Inverso
Para un manipulador con $N$ grados de libertad, conocemos que: $^0T_n= \begin{bmatrix} ^0R_n(q) & ^0P_{norig}(q)  \\ 0 \dots 0&  1\\ \end{bmatrix}$

En el espacio cartesiano: $\begin{bmatrix} r{11} & r_{12} & r_{13} & p_x \\ r_{21} & r_{22} & r_{23} & p_y\\ r_{31} & r_{32} & r_{33} & p_z \\ 0 & 0& 0& 1\\ \end{bmatrix}$

Se pueden generar 12 ecuaciones para calcular las n incognitas:
	- 9 ecuacion vienen de la matriz de rotación en $^0T_n \rightarrow$ solo 3 ec independientes
	- 3 ecuaciones vienen de las componentes del vector de posición $^0P_{norig}(q)$ 
Problema: Aparecen Ec no lineales además de ser un problema no homogeneo de 6 ec y n incógnitas

> [!info]
> Las ecuaciones del modelo cinemático inverso permiten resolver el **PCI** con poco coste computacional

Alternativamente se puede resolver el PCI mediante enfoques numéricos:
?	
 - Métodos iterativos
 - Lentos con grán coste computacional
 - Aplicables a cualquier manipulador

> [!important]
> El PCI puede:
> 
> 1. No tener solución cuando la localización se encuentre fuera de su espacio de trabajo
> 
>  2. Tener mas de una solución, está relacionado con la cantidad de grados de libertad que dispone el robot y la posibilidad de evitar obstaculos
