
## Conceptos:

>[!Defs] **Conceptos:**
> 1. **Pivote:** Subcadena que coincide con la parte derecha de una producción 
> 2. **Prefijo Variable**:: Sea $\phi \beta t$ una cadena de símbolos y sea $\beta$ una subcadena pivote y $t$ un símbolo terminal. Se define un prefijo ciable como la secuencia de símbolos que se pueden formar de izquierda a derecha hasta el símbolo t.
> 	Sea $\phi \beta=u_1,u_2,u_3\dots u_r$ y dada $B \rightarrow \beta$ una producción de la gramática, un prefijo viable será cualquier subcadena de la forma $u_1,u_2,u_3,\dots u_i$ donde $1 \leq i \leq r$. Es decir: $u_1;u_1u_2lu_1u_2u_3\dots$
> 3. **Items/Configuración de una gramática**:: Será una producción representada entre $[,]$ y con un *'˙'* en la parte derecha de la producción

## Objetivo

Construir un **AFD** que reconozca los prefijos viables a partir de una gramática. Los estados del autómata finito determinista se obtienen en base a agrupar los items asociados con cada producción de la gramática.

La construcción de del *AFD* para el analizador SLR se basa en:
1. **Gramática aumentada** Sea S el símbolo inicial de una gramática $G$. Se define otra gramática $G'$ denominada **aumentada**, tal que el símbolo inicial de la gramática es $S'$ y aparece la producción $S' \rightarrow S$
2. **Operación de clausura** de un conjunto de items de una gramática: Sea $I$ el conjunto de items. La clausura de $I$, que denotaremos como clausura(I), será otro conjunto de items obtenidos por las reglas siguientes:
	1. $\{I\} \subset \{\text{clausura}(I)\}$   
	2. Si $[A \rightarrow \alpha \dot B \gamma]$ y existe la producción $B \rightarrow \beta$, entonces $[B \rightarrow \dot \beta]$ y $[A \rightarrow \alpha \dot B \gamma] \in \{\text{clausura}(I)\}$  
>[!example]
>![[Pasted image 20250103102032.webp]]

3. **Función GOTO**: Es una función de transición de esstados alcanzables a partir de uno dado y según el símbolo que haya en la entrada.
Sea $I$ un conjunto  de ítems, Sea $X$.Se define la función *goto* del conjunto de ítems $I$ dado un símbolo $X$ de la gramática, notad