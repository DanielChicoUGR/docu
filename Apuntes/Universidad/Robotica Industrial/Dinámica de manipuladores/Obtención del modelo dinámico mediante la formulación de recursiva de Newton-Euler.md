- Es un algoritmo recursivo 
- Se basa en operaciones vectoriales
- El orden del algoritmo es $O(n)$. Mas eficiente que la formulación lagrangiana
- Recorre los eslabones 2 veces, una en cada dirección:
	- Del eslabón 1 al n:
		- Calcula la posición, velocidad y aceleración del eslabón i a partir de los correspondientes del eslabón i-1 y del movimiento relativo de la articulación i
	- Del eslabón n al 1:
		- Calcula las fuerzas y pares que actúan sobre el eslabón i a partir de los correspondientes al eslabón i+1 y de la posición, velocidad y aceleración del eslabón i
- Basada en el equilibrio de fuerzas y pares (2a ley de Newton y EC de euler) para cada elemento (eslabón), i (1$\dots$n):
$$
\Sigma F_i = \frac{d}{dt}(m_i\vec{v_i})=m_i \dot{\vec{v_i}}
$$$$
\Sigma T_i=\frac{d}{dt}(I_iw_i)=I_i\dot{w_i}+w_i\times(I_iw_i)
$$
- Donde:
	- $F_i$ son las fuerzas ejercidas sobre el elemento i
	- $T_i$ son los pares ejercidos sobre el elemento i en torno a su centro de masas.
	- $m_i$ es la masa del elemento i
	- $I_i$ es el [[tensor de inercia]] del elemento i en torno a su centro de masas expresado en $\{S_i\}$.
		- ![[tensor de inercia]]
	- $\vec{v}$ y  $\dot{\vec{v}}$ son la velocidad y la aceleración lineal del centro de masas de la articulación i
	- $w$ y  $\dot{w}$ son la velocidad y aceleración angular de la articulación i

### Algoritmo de Newton-Euler
1. Asignar a cada eslabón un sistema de coordenadas de acuerdo con las normas de D-H
2. Establecer las condiciones iniciales
	-  Para el SC de la base (Suponiendo base fija):
		1. $^0w_0=[0,0,0]^t$ (velocidad angular)
		2. $\dot{^0w_0}=[0,0,0]^t$ (aceleración angular)
		3. $^0v_0=[0,0,0]^t$ (velocidad lineal)
		4. $^0\dot{v_0}=-[g_{x0},g_{y0},g_{z0}]^t$ (Aceleración lineal) 
	-  Para el extremo del robot:
		- Fuerza y par ejercidos externamente: $^{n+1}f_{n+1}$ $^{n+1}n_{n+1}$
	-  $z_0=[0,0,1]^1$
	- Para i=$1\dots n$:
		- $^ip_i \rightarrow$ vector que une el origen $\{S_{i-1}\}$ con el de $\{S_{i}\}$ expresado en $\{S_{i-1}\}$: $[a_i,d_i*sen(\alpha_i),d_i*cos(\alpha_i)]$  
		- $^is_i \rightarrow$ Coordenadas del centro de masas del eslabón i respecto al sistema $\{S_{i}\}$
		- $^iI_i \rightarrow$ Matriz de inercia del eslabón i expresado en un sistema paralelo al $\{S_{i}\}$ y con origen en el centro de masas del eslabón
- Para i=$1\dots n$ (Se obtienen las componentes de las velocidades y aceleraciones de la base al efector):
	3. Obtener la matriz de rotación $^{i-1}R_i$ y su inversa $^{i}R_{i-1}=(^{i-1}R_{i})^T$
	4. Obtener la velocidad angular del sistema $\{S_{i}\}$:
		- Si i es de rotación: $^i\omega_i=^{i}R_{i-1}(^{i}\omega_{i-1}+z_0\dot{q_i})$ 
		- Si i es de traslación: $^i\omega_i=\ ^{i}R_{i-1} \ ^{i-1}\omega_{i-1}$ 
	5. Obtener la aceleración angular del sistema $\{S_{i}\}$:
		- Si i es de rotación: $^i\dot{\omega}_i=^{i}R_{i-1}(\ ^{i}\dot{\omega}_{i-1}+z_0\ddot{q_i}) + \ ^{i}\omega_{i-1}+z_0\dot{q_i}$   
		- Si i es de traslación: $\dot{^i\omega_i}=\ ^{i}R_{i-1} \ ^{i-1}\dot{\omega}_{i-1}$ 
	6. Obtener la aceleración lineal del sistema $\{S_{i}\}$:
		- Si i es de rotación: $^i\dot{v}_i=\ ^{i}\dot{\omega}_{i} \times \ ^ip_i + \  ^{i}{\omega}_{i} \times (\ ^{i}{\omega}_{i} \times \ ^ip_i) + \ ^iR_{i-1} \  ^{i-1}\dot{v}_{i-1}$    
		- Si i es de traslación: $\dot{^iv_i}=\ ^iR_{i-1}(z_0\ddot{q}_i + \ ^{i-1}\dot{v}_{i-1}) + \ ^i\dot{\omega}_i \times \ ^ip_i + 2\ ^iw_i \times ^iR_{i-1}z_0\dot{q}_i + ^iw_i\times(\ ^iw_i \times \ ^ip_i)$
	7. Obtener la aceleración lineal del centro de gravedad del eslabón i:
		- $^ia_i=\ ^i\dot{\omega}_i \times\ ^is_i +\ ^iw_i \times(\ ^iw_i +\ ^is_i) +\ ^i\dot{v}_i$ 
- Para $i=n\dots 1$ (Se obtienen los pares de fuerza del efector a la base):
	8. Obtener las fuerzas sobre el eslabón i:
		- $^if_i=\ ^iR_i+1\ ^{i+1}f_{i+1}+m_i\ ^ia_i$ 
	9. Obtener el par ejercido sobre el eslabón i:
		- $^in_i =\ ^iR_{i+1}[\ ^{i+1}n_{i+1} + (\ ^{i+1}R_i\ ^ip_i)\times\ ^{i+1}f_{i+1}]+(\ ^ip_i+\ ^is_i)\times m_i\ ^ia_i +\ ^iI_i\ ^i\dot{\omega}_i +\ ^iw_i\times(\ i^I_i\ ^iw_i)$
	10. Obtener la fuerza o par aplicado a la articulación i:
		- Si i es de rotación: $\tau_i=\ ^in_j^T\ ^iR_{i-1}z_0$ 
		- Si i es de traslación: $\tau_i=\ ^if_j^T\ ^iR_{i-1}z_0$


### Ejemplo algoritmo sobre Robot TL

![[Pasted image 20230604125845.png]]
![[Pasted image 20230604125907.png]]
![[Pasted image 20230604125918.png]]
![[Pasted image 20230604125931.png]]
![[Pasted image 20230604125943.png]]
![[Pasted image 20230604125950.png]]
![[Pasted image 20230604130002.png]]
![[Pasted image 20230604130012.png]]
![[Pasted image 20230604130020.png]]
![[Pasted image 20230604130031.png]]