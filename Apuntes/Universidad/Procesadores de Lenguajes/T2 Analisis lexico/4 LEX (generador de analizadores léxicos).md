## Introducción

![[Pasted image 20241106111657.webp]]

- Generador de analizadores de léxico: **LEX**

## Especificación lex

![[Pasted image 20241106111758.webp]]

### Programa básico lex

```cpp
{Definiciones}
%%
{Reglas}
%%
{Procedimientos de usuario}
```

### Operadores LEX

| Operador | Definición                                                                                                                                         |
| -------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| *        | Especifica la repetición de 0 o mas veces                                                                                                          |
| +        | Especifica la repetición de 1 o mas veces                                                                                                          |
| ( )      | Agrupa sub-expresiones                                                                                                                             |
| ?        | Especifica la opcionalidad del caracter precedente <br>(`ab?c` conoce `ac` y `abc`)                                                                |
| \[ ]     | Define una clase de caracteres. <br>(`[yx]` representa `x` o `y`)                                                                                  |
| \[m - n] | El operador `-` entre corchetes define un rango de caracteres entre `m` y `n` según la tabla *ascii*. Fuera de los corchetes carece de significado |
| \[^x]    | Indica cualquier caracter menos el indicado/s entre corchetes                                                                                      |
| \[\\]    | Indica una constante de tipo carácter siguiendo la notación del lenguaje C como rangos de caracteres imprimibles.                                  |
| ^        | Comienzo de línea                                                                                                                                  |
| $        | Final de linea                                                                                                                                     |
| .        | Cualquier patrón no especificado                                                                                                                   |
| "x"      | Especifica que el carácter entre comillas no es un operador lex<br>(`"$"`) no implica el fin de linea                                              |
| \\x      | Igual al caso anterior pero para un solo caracter                                                                                                  |
| { }      | Especifica un patrón definido anteriormente                                                                                                        |
| x{m,n}   | Especifica que el caracter `x` aparece desde `m` hasta `n` veces                                                                                   |
| x/y      | Reconoce el caracter `x` $\leftrightarrow$ va seguido del caracter `y`                                                                             |
| \\n      | Fin de linea                                                                                                                                       |
| \t       | Tabulación                                                                                                                                         |
| \\\\     | Símbolo $                                                                                                                                          |
| \b       | Espacio en blanco                                                                                                                                  |
