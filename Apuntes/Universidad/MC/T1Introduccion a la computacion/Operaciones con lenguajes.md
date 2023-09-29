


## Indice
- [[#Unión:|Unión:]]
- [[#Intersección|Intersección]]
- [[#Concatenación|Concatenación]]
		- [[#Propiedades|Propiedades]]
- [[#Potencia o iteración|Potencia o iteración]]
- [[#Clausura positiva:|Clausura positiva:]]
- [[#Clausura de Kleene:|Clausura de Kleene:]]
		- [[#Propiedades:|Propiedades:]]
- [[#Reflexión o Lenguaje Inverso:|Reflexión o Lenguaje Inverso:]]
- [[#Cabecera:|Cabecera:]]
- [[#Homomorfismo|Homomorfismo]]
		- [[#Propiedades:|Propiedades:]]

## Unión:
**Definición**:: Si $L_{1}$ y $L_{2}$ son dos lenguajes, su unión, $L_{1}\cup L_{2}$, contendrá todas las palabras que pertenezcan a cualquiera de los dos lenguajes $$L_{1}\cup L_{2} = \{x | x \in L_{1} \lor x \in L_{2}\}$$
## Intersección
**Definición**:: Si $L_1$ y $L_2$ son lenguajes, su intersección, $L_{1}\cap L_{2}$, contendrá todas las palabras que pertenezcan a los dos lenguajes $$L_{1}\cap L_{2} = \{x | x \in L_{1} \land x \in L_{2}\}$$ 
## Concatenación
**Definición**:: Dados dos lenguajes, $L_1$ y $L_2$, su concatenación $L_1L_2$, contendrá todas las palabras que se pueden formar por al concatenación de una palabra de $L_1$ y otra de $L_2$

Dado un lenguaje L sobre un alfabeto A, $L \subseteq A$ $$L_{1}L_{2}=\{uv | u \in L_{1}\land v \in L_{2}\}$$ 
#### Propiedades
?
- $L\varnothing=\varnothing L=\varnothing$ 
- $\{\epsilon\}L=L\{\epsilon\}=L$ -> Elemento neutro
- $L_{1}(L_{2}L_{3})=(L_{1}L_{2})L_{3}$ -> asociativa

## Potencia o iteración
**Definición**:: La potencia de un lenguaje corresponde a la concatenación i veces del lenguaje con él mismo. $$L^{i}=LL\dots L$$
Por definición: $$\forall L_{i},L_{1}^{0}=\{\epsilon\}$$

## Clausura positiva:
**Definición**:: Se forma por la unión de todas las potencias del lenguaje, excluyendo la potencia 0 $$L^{+}= \cup_{i\geq 1}L^{i}$$

## Clausura de Kleene:
**Definición**::Se forma por al unión de todas las potencias del lenguaje $$L^{*} = \cup_{i\geq 0}L^{i}$$
#### Propiedades:
?
- $L^{+}=L^{*} \text{ si } \epsilon \in L$
- $L^{+}=L^{*} - \epsilon \text{ si } \epsilon \notin L$   

## Reflexión o Lenguaje Inverso:
**Definición**::El lenguaje inverso de L está formado por la aplicación de la inversa a cada una de las palabras del lenguaje $$L^{-1} = \{u | u^{-1} \in L\}$$

## Cabecera:
**Definición**::La cabecera de un lenguaje L es el lenguaje dado por:$$\text{CAB}(L)=\set{u | u \in A^{*} \text { y } \exists v \in A^{*} \text{ tal que }uv \in L }$$

## Homomorfismo
**Definición**::Sean $A_{1}$ y $A_{2}$ dos alfabetos y una aplicación $h:A_{1}^{*} \rightarrow A_{2}^{*}$. Se dice que h es un *homomorfismo* $\iff$ $h(uv)=h(u)h(v)$

#### Propiedades:
? 
- $h(\epsilon)= \epsilon$
- $h(a_{1},\dots, a_{n})=h(a_{1})\dots h(a_{n})$
