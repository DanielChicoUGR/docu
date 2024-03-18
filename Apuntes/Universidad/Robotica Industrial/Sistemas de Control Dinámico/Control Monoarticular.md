# Características:

- El sistema de control gestiona de manera individual cada articulación
- La influencia del resto del sistema robótico es considerada como un par perturbador que se suma al resto de fuerzas/pares externos
![[Pasted image 20230603181407.png]]
- Los terminos J y B son respectivamente la inercia y el rozamiento viscoso que ha de vencer el actuador y $\tau_p$ son los pares perturbadores (fuerzas externas al actuador que interactuan con el mismo)
- El sistema de control adapta la tensión de mando (señal u) de forma que la trayectoria real q sea lo mas parecida posible a la trayectoria desea $q_d$ 

# Control Pre-alimentado (bucle abierto)
![[Pasted image 20230603181800.png]]
- La trayectoria real, q, en el dominio transformado puede expresarse como: $$q(s)=\frac{1}{(Js+b)s}[KH(s)q_d(s)-\tau_p(s)]$$
	- Haciendo $H(s)=\frac{1}{k}(Js+B)s$
	- $$q(s)=q_d(s)-\frac{1}{(Js+b)s}\tau_p(s)$$ En ausencia de perturbaciones q coincide con $q_d$
- Requiere un conocimiento preciso del motor y de la articulación (K,J y B )
- No requiere realimientación

# Control Prealimentado (bucle abierto)
![[Pasted image 20230603184954.png]]
- La trayectoria real, q, en el dominio transformado puede expresarse como: $$q(s)=\frac{1}{(Js+b)s}[e(s)KR(s)-\tau_p(s)]$$
	- Dado que $e(s)=q_d(s)-q(s)$ (error=tray.id-tray.real)$$
	  q(s)=\frac{KR(s)q_d(s)-\tau(s)}{(Js+B)s+KR(s)}=
	  \frac{KR(s)q_d(s)}{(Js+B)s+KR(s)}
	  -\frac{\tau(s)}{(Js+B)s+KR(s)}
							  $$ Primer sumando -> $q_c(s)$, Segundo sumando -> $q_p(s)$ 
  - Las perturbaciones introducen una componente $q_p(s)$ en q(s)
  - Nos interesa su comportamiento pasado un tiempo razonable (t=inf, s=0 en transformada de Laplace)

## Control Realimentado (Reguladores -> R(s) )

![[Regulador P]]


![[Regulador PI]]

# Control Rea