Basado en la función *Lagrangiana*:
$$L=E_c-E_p$$
Donde:
- $E_c \rightarrow$ Energía cinética (depende de $q$ y $\dot{q}$)
- $E_p \rightarrow$ Energía potencial (Depende de $q$)

Usa **matrices de transformación homogénea** obtenidas a partir del modelo de Devanit-Hartemberg

Es un proceso infeciente $\rightarrow$ Operaciones innecesarias debido a información redundante al representar orientaciones como matrices de rotación

Gran complejidad computacional $O(n^2)$. Siendo n los GDL 

No es apropiado para robots complejos (>6GDL) debido a la imposibilidad de realizar en tiempo real las operaciones que necesita

Conduce a ecuaciones finales bien estructuradas

## Algoritmo de Lagrange
1. Asignar a cada eslabón un SC de acuerdo al algoritmo de D-H
2. Obtener las matrices de transformación $^0T_i (i=0,\dots,n)$ 
3. Obtener las matrices $U_{ij}$ como:
   $U_{ij}=\frac{\partial\ ^0T_i}{\partial q_j}, i,j=1,\dots\,$
	   - 


