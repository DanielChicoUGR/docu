
## Descripción Funcional

>[!def] ¿Qué hace el analizador léxico?
>?
>Lee, carácter a carácter, del documento de entrada (texto fuente) y genera una secuencia de patrones léxicos denominados *tokens* y, en su caso, asocia *atributos* a los tokens.
>![[Pasted image 20241105122851.webp]]

### Aportaciones del analizador léxico

Simplifica el diseño del ***analizador sintáctico***, confiriéndole una mayor eficacia.

## Conceptos básicos

>[!def]
>**TOKEN**::Conjunto de secuencias de caracteres con la misma misión *sintáctica*
>**LEXEMA**:: Secuencia de caracteres que forman un *token*
>**PATRON**:: Regla o reglas que describen a los lexemas asociados a un *token*

>[!example]
>![[Pasted image 20241105123208.webp]]

