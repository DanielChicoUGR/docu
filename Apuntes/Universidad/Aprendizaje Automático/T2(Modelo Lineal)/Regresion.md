## Qué es?

*Regresión lineal*::Herramienta estadística que intenta modelar la relación entre varias variables y una valor real.

Traducido a un problema de aprendizaje, $X \subset{R^{d}}, \forall d \in \mathbb{N}$, Y sería el conjunto de etiquetas que en este caso es un valor real.  

## Elementos de un problema de Regresión
?
- $h(x)=w^Tx$ será la predicción de la regresión
	- Su expresión matemática sería: 
- Se usa el error cuadrático médio para medir la pérdida de $h_{w}(x)$ con $f$
	- Error($x$)= $(h_{w}(x)-f(x))^2$ -> Error para un punto del dataset
	- $E_{in}(h_{w})=\frac{1}{N} \Sigma^{N_{i=1}}(h_{w}(x_{i})-y_{i})$ -> Error dentro de la muestra.
- Eligiremos un $h_{w}$ tal que $\downarrow\downarrow\downarrow E_{in}$, aunque el objetivo es $\downarrow\downarrow E_{out}$
- $E_{out}(h)=\mathbb{E}(x,y)\thicksim p[(h(x)-y)^{2}]$
	- $\mathbb{E} \rightarrow$ Esperanza o media al elegir un elemento de manera aleatoria de la poblaión
- $$\hat{h}=h(X):min(E_{out}(h))$$ $\hat{h}\rightarrow$
- 