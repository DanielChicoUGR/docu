# Transformada de Laplace

Herramienta que sirve para el estudio de sistemas lineales en el dominio del tiempo, cuyo comportamiento se modela mediante ecuaciones diferenciales.

Transforma ecuaciones diferenciales (complicadas en el dominio del tiempo) en ecuaciones algebraicas (Dominio en $Z$ para tiempo discretizado)

Transformada de Laplace para una función $f(t)$ dependiente del tiempo: $$

F(s)=L(f(t))=\int_{0}^{\infty}f(t)e^{st}dt
$$ siendo $s$ una variable compleja

Transformada inversa de Laplace dado $L(T)$: $$
f(t)=L^{-1}(F(s))=\frac{1}{2\pi j} \lim_{T \rightarrow \infty }{\int_{c-jT}^{c+jT}F(s)e^{st}ds}
$$ donde $j=\sqrt{-1}$ y c es un numero real que deja a su izquierda todas las sigularidades de F(s) (mayor que todos los 0?)

## Propiedades

1. Linealidad $\rightarrow L(a *f(t)+b*g(t))=aF(s)+bG(s)$
2. Transformada de la derivada $\rightarrow L(\frac{df(t)}{dt})=sF(s)f(0)$
3. Transformada de la integral $\rightarrow L(\int_{0}^{t}f(\tau)d\tau)=\frac{F(s)}{s}$
4. Teorema del valor final $\rightarrow f(t=\infty)=  \lim_{s \rightarrow \infty }{sF(s)}$
5. Teorema del valor inicial $\rightarrow f(t=0)=\lim_{s \rightarrow \infty}sF(s)$

## Ejemplos

### Función escalón unitario

![[Pasted image 20230603122337.png]]$$u(t)= \left \{ \begin{array}{lcc}  
1 & t \ge 0 \\  
\\ 0 & t < 0 \\
\end{array}
  \right.
$$

$$
U(s)=\int_{0}^{\infty}u(t)e^{-st}dt=\frac{1}{s}
$$

## Sistema LTI (Lineal invariante en el tiempo)

- Es un sistema que se mantiene inmutable en el tiempo
- Son una buena aproximación a los sistemas físicos reales
- Se describen mediante un operador que transforma una señal de entrada en una señal de salida
- Puede usarse tanto en sistemas analógicos (dominios continuos) como en sistemas digitales (dominios discretos)
- Características:
	- Causalidad $\rightarrow$ Un sistema es causal si la respuesta se produce siempre después de la entrada
	- Estabilidad $\rightarrow$ Un sistema es estable si para una entrada finita se produce siempre una respuesta finita

### Función de transferencia de un sistema LTI
$$H(s)=\frac{Y(s)}{X(s)}$$ El cociente entre la transformada de salida y la de entrada, bajo la suposición de que las condiciones iniciales son nulas

Raices numerador -> ceros
Raices denominador -> polos