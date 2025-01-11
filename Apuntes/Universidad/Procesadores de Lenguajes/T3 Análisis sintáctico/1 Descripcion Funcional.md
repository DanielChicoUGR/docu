## Objetivo

Analizar las *secuencias de tokens* y comprobar que son *correctas sintácticamente*. 

A partir de secuencias de tokens, el analizador sintáctico nos devuelve:
1. Si la secuencia es *correcta* o *incorrecta* sintácticamente (es decir, existe un conjunto de reglas gramaticales aplicables para poder estructurar las secuencias de *tokens*).
2. El *orden* en el que hay que aplicar las producciones de la gramática para obtener la secuencia de entrada (**árbol sintáctico**)

![[Pasted image 20241106132214.webp]]

Si no se encuentra un árbol sintáctico para una secuencia de entrada, entonces la secuencia de entrada es incorrecta sintácticamente (tiene errores sintácticos)


