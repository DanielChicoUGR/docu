## Indice
- [[#Concatenación:|Concatenación:]]
		- [[#Propiedades:|Propiedades:]]
- [[#Potencia/Iteración|Potencia/Iteración]]
		- [[#Propiedades:|Propiedades:]]
- [[#Reflexión|Reflexión]]

## Concatenación:
**Definición**::si $u,v \in A^{*},u=a_{1},\dots a_{n}, v=b_{1},\dots,b_{n}$, se llama concatenación de $u \text{ y } v$ a la cadena $u \cdot v$ (o simplemente $uv$) dada por $a_{1},\dots a_{n},b_{1}\dots b_{n}$ 

```ad-example
si $u=011,v=1010$, entonces $uv=0111010$
```

#### Propiedades:
?
- $|uv|=|u|+|v|, \forall u,v \in A^{*}$
- *Asociativa* -> $u(vw)=(uv)w, \forall u,v,w \in A^{*}$ 
- *Elemento Neutro*: $u\epsilon=\epsilon u=u,\forall u \in A^{*}$ 
- *Estructura de monoide* -> ![[Pasted image 20230926122023.png]]

## Potencia/Iteración
**Definición**:: La potencia i-ésima de una palabra $u$, se denota como $u^{i}$ y es el resultado de concatenar $u$ consigo misma $i$ veces

#### Propiedades:
?
- $u^{0}=\epsilon$
- $u^{i+1}=u^{i}u, \forall i \ge 0$ 

```ad-example
Si $u=101$, entonces $u^3=010010010$
```

## Reflexión
**Definición**:: Si $u$ es una palabra formada por una secuencia de símbolos entonces la palabra $u^{-1}$ se forma invirtiendo el orden de los símbolos.$$ u = u_{1},\dots,u_{n}\in A^{*}, \text{ entonces } u^{-1}=u_{n},\dots, u_{1} \in A^{*}$$
```ad-example
Si $u=011$, entonces $u^{-1}=110$
```
 