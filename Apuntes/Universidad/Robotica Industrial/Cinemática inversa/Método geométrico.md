Es adecuadoo para robots con pocos GDL o cuando se consideren solo los primeros GDL, dedicados a posicionar el efector.

Busca las relaciones geométricas en las que intervengan las coordenadas del efectir, sus coordenadas articulares y las dimensiones físicas de sus elementos.

## Ejemplo de Robot TRR
![[Pasted image 20230530190026.png]]
$q_1=arctan \frac{p_y}{p_x} \rightarrow$ Fijado $q_1$ el robot tiene estructura planar.

Calculamos $q_3$
$cos(q_3)=\frac{p_x^2+p_y^2+p_z^2-l_2^2-l_3^2}{2*l_2*l_3}$
$sin(q_3)=\pm\sqrt{1-cos^2(q_3)}$ 

Calculamos $q2$
$q_2=\alpha-\beta$
$\beta=arctan \frac{p_z}{r}= arctan \frac{p_z}{\pm\sqrt{p_x^2+p_y^2}}$
![[Pasted image 20230530190240.png]]  ![[Pasted image 20230530190300.png]]
