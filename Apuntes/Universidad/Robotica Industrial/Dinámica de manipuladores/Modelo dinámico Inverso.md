# Se define como: 
$$\tau=D\ddot{q}+H+C$$
- Donde:
	- $q$ es el vector de coordenadas articulares
		- $\dot{q}$ derivada del vector de coordenadas (velocidad)
		- $\ddot{q}$ segunda derivada del vector de coordenadas (aceleración)
	- $\tau$ es el vector de fuerzas (o pares efectivos) que se aplican a cada articulación. Tiene en cuenta los pares perturbadores y el rozamiento
	- $D(q)$ es la matriz de inercia, de dimension $(n \times n)$ cuyos elementos son función de *q*
	- $H(q,\dot{q})$ es la matriz $(1 \times n)$ de fuerzas de coriolis y centrifugas, dependiente de *q* y $\dot{q}$ 
	- $C(q)$ es la matriz de inercia, de dimension $(n \times 1)$ cuyos elementos dependen de de *q*
