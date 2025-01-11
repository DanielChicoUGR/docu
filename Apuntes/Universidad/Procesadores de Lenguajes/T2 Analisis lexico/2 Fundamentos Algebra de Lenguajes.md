
>[!th] Construcción de Thompson
>?
>A toda expresión regular le corresponde un AFN. La construcción de *Thompson* permite obtener el *AFN* asociado a una expresión regular dada. 

## Implementación del analizador léxico:

>[!defs]
**Autómata reconocedor de patrones**::AFD con anticipación
**Autómata reconocedor de palabras**::AFD+Tabla de palabras reservadas

## Gramática abstracta y Tabla de tokens

>[!defs]
**Gramática abstracta**::Gramática resultante de considerar los tokens como símbolos terminales y eliminar aquellas producciones en las que derivan los tokens.
**Tabla de símbolos**::Lugar de almacenamiento temporal (durante la fase de compilación y, en lenguajes orientados a objetos, durante la ejecución) debido a la necesidad de identificar los lexemas en la ocurrencia de cada token durante las fases posteriores de traducción
**Tabla de tokens**::Tabla formada por tantas filas como tokens se hayan identificado. Las columnas tienen la siguiente información: Token, Código, Atributos y Patrón.


### Generar gramática abstracta

![[Pasted image 20241105160714.webp]]

![[Pasted image 20241105160735.webp]]

![[Pasted image 20241105160752.webp]]

![[Pasted image 20241105160815.webp]]
