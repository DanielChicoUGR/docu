
# Introducción
Un algoritmo de aprendizaje recibe un dataset de entrenamiento $S$, extraido de una distribución de probabilidad $D$ y caracterizado/etiquetado por una función $f$. Debería producir una hipótesis $h_{s}=X \rightarrow Y$. El objetivo es que ese $h_{s}$ que devuelve el algoritmo minimice el error dependiente de $D$ y $f$ que son desconocidas.

Al ser desconocidas el algoritmo de aprendizaje no puede acceder al *error verdadero*. Un error que puede calcular el algoritmo es el *training error*:: error que la hipótesis devuelta por el algoritmo tiene sobre la muestra.
$$L_{s}(h)=^{def}=\frac{|\{i \in [m] : h(x_{i}) \ne y_{i}|}{m}$$
El error empírico y riesgo empírico (empirical error and empirical risk) son términos que se usan indistintamente para referirse a este concepto.


# ERM
Entrenar con una muestra es como tomar una foto del mundo e intentar aprender de la misma. Es una buena estrategia buscar soluciones que funcionen bien con los datos. 
Este paradigma: **Buscar una hipótesis $h$ que minimice $L_{S}(h)$ se denomina *Empirical Risk Minimization***.