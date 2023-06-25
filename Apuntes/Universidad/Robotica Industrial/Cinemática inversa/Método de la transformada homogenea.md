Tiene su base en el [[Método Algebraico]] aprovechandose de las propiedades del producto de transformadas es posible reducir la complejidad.


## Ejemplo Robot TRL
![[Pasted image 20230530191254.png]]![[Pasted image 20230530191300.png]]
#### Tabla Devanit-Hartenberg del robot

| i   | $\theta_i$ | $d_i$ | $a_i$ | $\alpha_1$ |
| --- | ---------- | ----- | ----- | ---------- |
| 1   | $q_1$      | $l_1$ |    0   | 90         |
| 2   | $q_2$      | 0     | 0     | -90        |
| 3   | 0          | $q_3$ | 0     | 0           |

#### Matrices de Transformada homogenea:
- $^0T_1=\begin{bmatrix} C_1 & 0 & S_1 & 0 \\ S_1 & 0 & -C_1 & 0\\ 0 & 1 & 0 & l_1 \\ 0 & 0& 0& 1\\ \end{bmatrix}$ 
- $^1T_2=\begin{bmatrix} C_2 & 0 & -S_2 & 0 \\ S_2 & 0 & C_2 & 0\\ 0 & -1 & 0 & 0 \\ 0 & 0& 0& 1\\ \end{bmatrix}$
- $^2T_3=\begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0\\ 0 & 0 & 1 & q_3 \\ 0 & 0& 0& 1\\ \end{bmatrix}$ 
- $^0T_3=^0T_1 * ^1T_2 * ^2T_3=\begin{bmatrix} C_1C_2 & -S_1 & -C_1S_2 & -q_3C_1S_2 \\ S_1C_2 & C_1 & -S_1S_2 & -q_3S_1S_2\\ S_2 & 0 & C_2 & q_3C_2+l_1 \\ 0 & 0& 0& 1\\ \end{bmatrix}$ 
Igualamos $^0T_3$ a la matriz de transformada homogénea correspondiente a la posición y orientación deseadas (conocidas), $U$, y "Despajamos" $q_1,q_2$ y $q_3$ 