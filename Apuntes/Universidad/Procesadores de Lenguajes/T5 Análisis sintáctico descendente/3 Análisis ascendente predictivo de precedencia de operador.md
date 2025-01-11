Resuelve la acción alternativa (ante posibles conflictos desplaza/reduce) en base a criterios de precedencia de operadores. El *análisis de precedencia de operadores* es aplicable a lenguajes definidos por *gramáticas* con las siguientes *restricciones*:
1. No podrán aparecer *dos símbolos no terminales consecutivos* en las producciones
2. No podrán existir *producciones a la cadena vacía*
3. Las *relaciones de precedencia* deben ser **[[__Relaciones Disjuntas|Disjuntas]]** 
La *tabla de análisis de precedencia* de operador está formada *únicamente* por *símbolos terminales* puestos de la siguiente forma:
![[Pasted image 20241112123722.webp]]

>[!example]
>![[Pasted image 20241112123835.webp]]

>[!warning] Problemas:
>- **No contempla** la posibilidad de que haya tokens con **doble precedencia**.
>	- El operador “menos” tiene más precedencia cuando actúa como unario y menos precedencia cuando actúa como binario.
>- El algoritmo puede aceptar entradas que no se corresponden con la sintaxis
>	- Ejemplo: id++id. Se debe a que no comprueba la parte derecha de las producciones antes de realizar la eliminación de símbolos en la pila (reducción).

## Métodos para obtener las relaciones de precedencia de operador

1. **Método intuitivo:** Basado en el sentido común y asociado con las reglas del cálculo en donde se aplica una precedencia de cálculo según una precedencia de operadores. Se conoce el lenguaje en virtud de la gramática y es sencillo extraer las relaciones de precedencias.
2. **Método deductivo:** Basado en el análisis de las gramáticas mediante el desarrollo de los árboles de análisis. Como requisito, las gramáticas deben ser no ambiguas. Útil cuando la gramática no permite determinar las precedencias.
3. **Método asociativo:** Basado en la asociatividad de los operadores y en las reglas de precedencia de operadores para el cálculo. Método general de resolución de conflictos en base a precedencia y asociatividad.
