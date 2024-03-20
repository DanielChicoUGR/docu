
## Gramática Formal
?
Se define como una cuadrupla $(V,T,P,S)$ donde:
- *V* -> Alfabeto de las variables o símbolos no terminales (Suelen representarse en MAYUS)
- *T* -> Alfabeto de los símbolos terminales (Suelen representarse en minus)
- *P* -> Conjunto finito de reglas o producciones de la forma $(\alpha,\beta)$ donde $\alpha,\beta \in (V \cup T)^{*}$ y $\alpha$ contiene al menos un símbolo de *V*
- *S* -> elemento de *V* denominado símbolo de partida o axioma

> [!note] Utilidad
> Una gramática sirve para determinar un lenguaje. Las palabras pertenecen a $T^{*}$ y se obtienen a partir del símbolo inicial aplicando [[Gramáticas#^1yusgw|derivacion]]. Cada paso consiste en elegir una parte de la palabra qeu coincida con la parte izquierda de una producción y sustituirla por lo que aparece a la derecha de la misma.

## Definiciones:

**Derivación**:: sea la gramática $G=(V,T,P,S)$ y dos palabras $\alpha,\beta \in (V \cup T)^{*}$, $\beta$ es la derivación de $\alpha, (\alpha \dot\rightarrow \beta) \ \iff$ existe una sucesión de palabra $\gamma_{1},\dots \gamma_{n}, (n \geq 1)$ tales que $a=\gamma_{1} \Rightarrow\gamma_{2} \Rightarrow \dots  \Rightarrow\gamma_{n} =\beta$        ^1yusgw

**Lenguaje Generados por una Gramática**:: Es el conjunto de todas las cadenas formadas por símbolos terminales y que son derivables a partir del símbolo de partida. $$L(G)=\set{u \in T^{*} | S \dot \Rightarrow u}$$
**Equivalencia de gramáticas**:: Dos gramáticas $G_{1}$ y $G_{2}$ son equivalentes si generan el mismo lenguaje.

## Árboles de derivación
?
- Son una forma de presentar las derivaciones
- Solo se pueden definir para gramáticas de [[Jerarquía de Chomsky#Tipo 1 (Dependientes del contexto) |Tipo 1]] o más restrictivas

![[Pasted image 20230926180204.png]]

### Construcción
? 
- [[Gramáticas#^o27ybp|El axioma]] se representa en la raíz
- Las hojas son símbolos terminales
- Los nodos intermedios son símbolos no terminales
- Las derivaciones se representan creando tantos sucesores del símbolo no terminal de la izquierda de las producciones como símbolos aparezcan en la parte derecha de las producciones


## Ambigüedad
?
Se presenta cuando existe más de una forma de generar una palabra a partir del símbolo inicial de una gramática. Impide que el análisis de palabras sea determinista

### Niveles:
#### Palabra
Una palabra es ambigua si tiene más de una derivación o árbol de derivación
#### Lenguaje
Un lenguaje es ambiguo si existe una gramática ambigua que lo genera. Un lenguaje en inherentemente ambiguo si todas las gramáticas que lo generan son ambiguas
#### Gramática
Una gramática es ambigua si tiene al menos una sentencia ambigua

## Recursividad:

**Producción recursiva**:: El mismo símbolo no terminal aparece en los dos lados de la producción. $\exists A \in V$ tal que $(A \rightarrow xAy) \in P; x,y \in T^{*}$ 

**Gramática recursiva**:: Contiene al menos una producción recursiva en su conjunto de producciones. Puede especializarse en *Recursiva por la Derecha* y *Recursiva por la Izquierda.*


> [!todo] Factorización
> Preguntar Profesor
