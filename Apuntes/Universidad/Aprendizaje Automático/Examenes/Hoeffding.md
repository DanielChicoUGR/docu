Tenemos la expresión de Hoeffding: $$\mathbb P[\mid \nu - \mu \mid > \epsilon] \le 2e^{-2\epsilon^{2} N}$$
En el que la probabilidad de sacar una bola roja (error) de la bolsa (ejemplo de la bolsa de los videos) sea mayor que epsilon(margen de error) viene acotada por la expresion de la derecha

Reescribiendo para ML, (para un conjunto de hipótesis) tenemos $$\mathbb P[|E_{in}(h)-E_{out}(h)|>\epsilon ] \le 2Me^{2\epsilon^2 N}$$

Y su consiguiente acotación del error:$$E_{out}(g) \le E_{in}(g) + \Omega(N,H,\delta)$$ con una probabilidad de $1- \delta$ 

El termino $\Omega$ indica la penalización por la complejidad del modelo (No influye en la pregunta del error).

La nueva función de error que dice la diapositiva iría en el cálculo de $E_{in}(g)$