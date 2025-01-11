
## Detección de errores

Se considera un error cuando ocurre una de las siguientes opciones:
1. Cuando no esté definida la relación de precedencia entre dos símbolos adyacentes de entrada: **Error de precedencia**
2. Cuando se ha obtenido un pivote para aplicar reducción y no existe ninguna producción con idéntica parte derecha al [[4 Análisis ascendente predictivo de precedencia simple#^c1ojh1|pivote]]. *Error de reducción*.

## Manejo de errores durante la reducción
Ante un error se actuará sacando el símbolo de la pila y notificar el error. Se distinguen dos casos:
1. Cuando el [[4 Análisis ascendente predictivo de precedencia simple#^c1ojh1|pivote]] no casa pero alguna subsecuencia **si**.
2. Cuando falte algún símbolo para poder aplicar con éxito la reducción.

No es trivial obtener un mensaje certero en análisis de precedencia. Cuando se detecta este tipo de error hay que decidir qué símbolos de la pila hay que sacar.

Como solución se propone explicitar una primacidad de un operador sobre otro en base a su orden de aparición en la tabla de precedencia.