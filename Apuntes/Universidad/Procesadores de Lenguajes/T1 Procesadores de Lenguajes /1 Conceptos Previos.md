# Conceptos Previos

- ![[1 Conceptos Previos-20241028165651376.webp]]
- ![[1 Conceptos Previos-20241028165803916.webp]]

## Concepto de traducción
Cuando el lenguaje de especificación de un programa es diferente al lenguaje máquina es necesario traducirlo al lenguaje máquina para poder ejecutarlo.

![[1 Conceptos Previos-20241028170005930.webp]]
>[!note]
>Todo lenguaje de programación que no sea lenguaje máquina, describe ==una máquina virtual==.

El proceso de traducción relaciona a dos o más **modelos semánticos** (culturas). Un modelo semántico está formado por:
?
1. Lenguaje
2. Dominio semántico
3. Interpretación

>[!abstract] *Lenguaje*
>?
>Un lenguaje es un conjunto de construcciones simbólicas formadas por secuencias de símbolos de un alfabeto. Se utiliza para representar los valores semánticos de un dominio semántico.
>
>Un lenguaje puede definirse:
>1. Por extensión -> Ejemplos
>2. Por comprensión -> A través de su gramática

>[!abstract] **Dominio semántico**
?
>Un token del lenguaje puede ser de dos tipos:
>1. Elementales
>2. Estructurados
>![[1 Conceptos Previos-20241028170705568.webp]]

>[!abstract] **Interpretación**
>Sea D un dominio semántico y $L(G)$ el lenguaje definido por la gramática G, Se define la *interpretación* como una aplicación $l$: $$I:L(G)\rightarrow D$$
>Se denota el modelo semántico (o modelo de la interpretación) como:$$M=(L(G),D,I)$$


## Requisitos para construcción de un traductor
?
Dados dos lenguajes, $L_1(G_1) \text{ y } L_2(G_2)$. Se necesitan construir dos modelos semánticos: $$M_1=(L_1(G_1),D_1,I_1) \text{ y } M_2=(L_2(G_2),D_2,I_2)$$Se debe cumplir: $$D_1 \subseteq D_2 \text{ y}$$ $$\forall \alpha \in L_1(G_1), \exists \beta \in L_2(G_2)\ / \ I_1(\alpha)=I_2(\beta)$$

>[!note]-
>1. Los elementos de representación ($D_i$) cumplen que el primero es un subset del segundo
>2. Para toda palabra construible por el lenguaje 1 existe otra palabra en el lenguaje 2 que cumplen que la interpretación de ambas es igual (equivalente).


## Esquema de Traducción
?
Dados los modelos semánticos:$$M_1=(L_1(G_1),D_1,I_1) \text{ y } M_2=(L_2(G_2),D_2,I_2)$$Se define un *Esquema de Traducción* como una función $T$:$$T:L_1(G_1)\rightarrow L_2(G_2) $$ verificándose que: $$\forall \alpha \in L_1(G_1), \exists \beta \in L_2(G_2) \text{ con } T(\alpha)=\beta \text{ y } I_1(\alpha)=I_2(\beta)$$

>[!note]-
>La función de traducción debe de reflejar la relación [[#Requisitos para construcción de un traductor|antes descrita]]

