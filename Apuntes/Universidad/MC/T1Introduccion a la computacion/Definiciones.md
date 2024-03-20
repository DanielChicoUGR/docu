## Indice
- [[#Alfabeto|Alfabeto]]
- [[#Palabra/ Cadena|Palabra/ Cadena]]
- [[#Lóngitud de una palabra $ u $| Longitud Palabra]] 
- [[#Palabra vacía $\epsilon$|Palabra vacía ]]
- [[#Universo de un Alfabeto: $A^*$|Universo de un Alfabeto]]
- [[#Lenguaje sobre un alfabeto:|Lenguaje sobre un alfabeto:]]

## Alfabeto
**Definición**::Conjunto no vacío finito de símbolos (numeros, letras combinaciones de ambos,...)
#### Notación
?
- Alfabetos -> A,B,C...
- Símbolos -> a,b,c,... (o numeros)
## Palabra/ Cadena

**Definición**::Secuencia finita de símbolos de un alfabetos. $u=a_1 \dots a_n$ donde $a_{i} \in A, \forall i = 1,\dots,n$ 
> [!example]
> Si $A=\{0,1\}$ entonces 1110 es una palabra del alfabeto A
#### Notación
?
-  Palabras: u,v,x,y,z


## Lóngitud de una palabra $|u|$
Definición:: dada una palabra $u$ formada por símbolos de una alfabeto A, su longitud es el número de símbolos del alfabeto que la forman.

## Palabra vacía $\epsilon$
Definición:: Palabra de longitud 0 no contiene ningún símbolo $|\epsilon|=0$

## Universo de un Alfabeto: $A^*$
Definición::Conjunto de todas las palabras que se pueden formar con símbolos del alfabeto. La palabra vacía pertenece a todos los universos. El conjunto de palabra sobre un alfabeto $A$ excluyendo la cadena vacía se representa como $A^+$ 

## Lenguaje sobre un alfabeto:
Definición:: Es todo subconjunto del universo del alfabeto. Dado un lenguaje $L$ sobre un alfabeto $A,L \subseteq A^*$

#### Notación
? 
-  Lenguajes: $L,M,N,\dots$

> [!example]
> - $L_1=\{a,b,\epsilon\}$ -> El lenguaje tiene 3 palabras
> - $L_2=\{a^ib^i|i=1,2,\dots\}$ -> Sucesión de a seguida de b de igual longitud
> - $L_{3}=uu^{-1}|u \in A^{*}$ -> Palindromo de longitud par
> - $L_{4}=\{a^{n^{2}}|n=1,2,3,\dots\}$ -> sucesiones de a iguales a un cuadrado

