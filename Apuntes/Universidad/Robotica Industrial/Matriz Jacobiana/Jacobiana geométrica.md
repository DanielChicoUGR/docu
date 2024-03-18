![[Pasted image 20230531171336.png]]

Se representa como $J$ y denomina jacobiana geométrica o jacobiana

Se obtiene a partir de la matriz de transformación homogénea pero de manera menos directa que la analítica.

La velocidad lineal del extremo del robot coincide con al definida en la [[Jacobiana analítica]]:
	- $v_x=\frac{dx}{dt}=\dot{x}$
	- $v_y=\frac{dy}{dt}=\dot{y}$
	- $v_z=\frac{dz}{dt}=\dot{z}$

La velocidad angular se obtiene a partir de la submatrix de rotación, **R**, de la transformada homogénea.

Para ello necesitamos definir una matriz $\Omega=\dot{R}*R^T$ 
	- A tener en cuenta que **R** es ortonormal: $R*R^T=I$ 
	- Al derivar esa expresión en función de R $\rightarrow$ $\dot{R}*R^T + R*\dot{R^T}=0$ 
	- El primer sumando corresponde a $\Omega$
	- El segundo sumando corresponde a $\Omega^T$ 

Se deduce que $\Omega$ es una matriz antisimétrica con la forma: $$
\Omega=\begin{bmatrix}
0 & -w_z & w_y \\
w_z & 0 & -w_x \\
-w_y & w_x & 0\\
\end{bmatrix}
$$Siendo $w_x,w_y,w_z$ las componentes de la velocidad angular


