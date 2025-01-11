## Gramáticas Libres del contexto

![[Pasted image 20241106132318.webp]]

## Árbol sintáctico
Es una **representación gráfica** donde aparecen las producciones de la gramática aplicadas y en el *orden* que son aplicadas para obtener una *secuencia de símbolos* de un lenguaje.

En las hojas aparecen *símbolos terminales* y en los nodos interiores aparecen *símbolos no terminales*.

>[!example]
![[Pasted image 20241106132530.webp]]

## Formas Normales

### Forma Normal de Chomsky (CNF)

Toda gramática libre del contexto cuyas producciones son de la forma:
- $A \rightarrow Bc$
- $A \rightarrow a$
Siendo `A` y `B` simbolos no terminales y `a` y `c` símbolos terminales

### Forma normal de Greibach (GNF)

Toda gramática libre del contexto cuyas producciones son de la forma:
- $A->a\beta$ 
Siendo A un símbolo no terminal, a un símbolo terminal y $\beta$ cualquier combinación de **símbolos no terminales** o la **cadena vacía**.

## Autómatas con Pila

>[!th] Teorema
>Si $L$ es un lenguaje libre de contexto, entonces existe un autómata de pila $N(M)$ tal que $L=N(M)$

>[!th] Teorema
>Si $L=N(M)$ para un autómata de pila, entonces $L$ es libre de contecto

## Estrategias de análisis 

### Estrategias Descendentes (TOP-DOWN)

Partir del símbolo inicial de la gramática y generar los árboles sintácticos hasta que se alcance la secuencia de símbolos $\omega$ 

Sea $S$ el símbolo inicial de la gramática. Se dice que $\omega$ es correcta sintácticamente al $S \Rightarrow ^*_G\omega$ 

![[Pasted image 20241106153425.webp]]

>[!example]
>![[Pasted image 20241106154006.webp]] 
>![[Pasted image 20241106154021.webp]]
### Estrategias ascendente(Bottom-Up) 

Partir de la propia secuencia $\omega$ y busca las subcadenas que coincidan con las partes derechas de las producciones y reescribirlas por la izquierda (**Reducción**) hasta que se llegue al símbolo inicial.

Sea $A \rightarrow \alpha$ una producción de la gramática $G$. Una reducción que $\alpha \rightarrow A$. Se denita las reducciones sucesivas como $\rightarrow ^*_G$.

Se dice que $\omega$ es correcta sintácticamente si se cumple que $\omega \rightarrow ^*_GS$ donde $S$ es el símbolo inicial de la gramática $G$. Es decir, aplicando reducción sucesivas a $\omega$ se alcanza $S$

![[Pasted image 20241106153435.webp]]

>[!example]
>![[Pasted image 20241106154006.webp]] 
>![[Pasted image 20241106154041.webp]]

