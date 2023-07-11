*VC analysis:*
aproximación in sample
Escoge un H que puede generalizar y tiene una buena probabilidad de ajustarse a los datos
Tiene en cuenta la complegidad del conjunto hipótesis H
$E_{out} \le E_{in} + \text{Error de Generalización}$
Error de generalizacion = $O(\sqrt{d_{vc} * \frac {log(N)} { N})}$
Con probabilidad >= 1 - $\delta$

Para $d_{vc}$ finita y N>>0 la generalizacion esta asegurada
	Modelo bueno --> buena generalizacion
	Modelo desconocido --> dvc infinita (sin respuesta en VC)

funcion de crecimiento $mH \le 2^N$
si $mH = 2^N$ 'shatter' (rompe?) el conjunto -> Clasifica

Inegualdad VC
$$P[\text{algo malo}] \le 4* \text{mH}(2N) * e^{-1/8 * E^{2*N}}$$



$$
\text{algo malo } \rightarrow |Ein(h) - Eout(h)|>\epsilon
$$

Una vez que sabemos que el conjunto H tiene un crecimiento polinomial podemos decir que
el aprendizaje es factible.

mH(k) < 2^k
k-> breakpoint
	Si no hay breakpoint mH = 2^N
	Si hay breakpoint mH = polinomial en N

Sauer-Shelah-Perles


$N \le d_{vc}(H)$ : H can 'shatter' (encajar? -> Separar) N points
$k > d_{vc}(H)$ : k is a break point for H

Para modelos lineales dvc=d+1 (se puede demostrar que cumple con
 $d_{vc} \le d+1$  y $d_{vc} \ge d+1$)

Sample complexity: mide el N minimo para alcanzar generalizacion
Como regla general N > 10 *dvc

*Bias-variance*
aproximación en general
Escoge H y A para aproximar f y no comportarse mal despues de ver los datos
Tiene en cuenta H y A
Error Cuadratico medio MSE

Ed -> Expected Value sobre conjunto datos D
$\mathbb E[E_{out}(g^{D})] = \text{ruido} + \text{bias} + \text{varianza}$


$\text{Varianza} = \mathbb E[(g^{D}(x) - \overline{g}(x))^2]$

La varianza es lo lejos que esta tu hipotesis sobre un conjunto de datos comparado con la "mejor hipotesis" (la media) de H

$\text{Bias} = (\overline g (x)-f(x))^2$
El bias lo lejos que esta la "mejor hypotesis" (la media) de f

mejor hipotesis entre comillas porque no es la mejor, es la media.
La mejor es por lo menos la media.