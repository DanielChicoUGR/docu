Es una matriz simétrica que caracteriza la inercia rotacional de un sólido rígido. Viene dado por: 
$$
\begin{bmatrix}
I_{xx} &-I_{xy} &-I_{xz} \\
-I_{yx} &I_{yy} &I_{yz} \\
-I_{zx} &I_{zy} &I_{zz}
\end{bmatrix}
$$

Donde:
- $I_{xx}=\int_{M}(y_p^2+z_p^2)dm$
- $I_{yy}=\int_{M}(x_p^2+z_p^2)dm$
- $I_{zz}=\int_{M}(x_p^2+y_p^2)dm$
- $I_{xy}=\int_{M}(x_p^2y_p^2)dm$
- $I_{xz}=\int_{M}(x_p^2z_p^2)dm$
- $I_{yz}=\int_{M}(y_p^2z_p^2)dm$
La posición de cada elemento viene dada por $^ip=[x_p,y_p,z_p]^T$ 