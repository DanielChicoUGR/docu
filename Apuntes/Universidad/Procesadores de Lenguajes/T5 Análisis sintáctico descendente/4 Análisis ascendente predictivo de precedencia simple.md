Propuesta por Wirth y Weber en 1966 como generalización de la precedencia de operador. Observaron que determinados símbolos terminales aparecen siempre adyacentes dependiendo de las producciones de la gramática, de tal forma que se puede establecer relaciones de precedencia entre símbolos terminales y no terminales.

Esta relación nos puede servir para determinar la **subcadena de entrada** que debe ser **reducida** o **desplazada**.

Se definen tres relaciones de precedencia entre símbolos terminales y no terminales ne base a su disposición en el árbol de análisis:
1. **Menor precedencia** $a < b$: Si $a$ cuelga de algún nodo superior a la izquierda del nodo que cuelga $b$.

2. **Mayor precedencia** $a > b$: Si $a$ cuelga de algún nodo superior a la derecha del nodo que cuelga $b$.

3. **Igual precedencia** $a \doteq b$: Si $a$ y $b$ cuelgan del mismo nodo.
![[Pasted image 20241112125320.webp]]

## Obtención del reglas de precedencia dado un árbol de precedencia

Dado un árbol de análisis, para definir las relaciones de precedencia se aplican las reglas siguientes:

1. Todos los símbolos que cuelgan de nodos superiores y están a la izquierda inmediatamente, son de menor precedencia, es decir:   $$
   X < Y \text{ si } A \rightarrow \alpha X B \beta \text{ y } B \Rightarrow^+ Y \gamma
   $$
2. Todos los símbolos que cuelgan de un mismo nodo son entre sí de igual precedencia, es decir:$$
   X \doteq Y \text{ si } A \rightarrow \alpha X Y \beta
   $$
3. Todos los símbolos que cuelgan de nodos superiores y están a la derecha, son de mayor precedencia, es decir: $$
   X > a \text{ si } a \in V_T \text{ y } B \rightarrow \alpha C a \beta \text{ y } C \Rightarrow^+ \gamma X
   $$
## Concepto de pivote

>[!def] **PIVOTE** Subcadena susceptible de ser reducida ^c1ojh1

El análisis de precedencia simple es aplicable a lenguajes definidos por gramáticas con las siguientes *restricciones*:
1. No podrán existir producciones cuya parte derecha sea la misma.
2. No podrán existir producciones a la cadena vacía.
3. Las relaciones de precedencia deben ser disjuntas.

### Proceso para determinar el Pivote:
Dada una secuencia de entrada, para determinar el pivote se obtiene la *relación de precedencia* entre los *símbolos adyacentes* y, cuando detectemos un *cambio de precedencia* de *menor/igual* a *mayor*, entonces los símbolos comprendidos entre las relaciones de menor y mayor precedencia formarán el **pivote** por el que se debe *reducir*.
>[!example]
![[Pasted image 20241112130354.webp]]


>[!example]
>![[Pasted image 20241112130742.webp]]

