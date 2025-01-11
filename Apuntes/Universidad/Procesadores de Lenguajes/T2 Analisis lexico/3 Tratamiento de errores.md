
## Estrategias de Recuperación

Un traductor debe adoptar alguna estrategia para detectar, informar y recuperarse para seguir analizando hasta el final. Las respuestas ante el error pueden ser: 
- **Inaceptables**: Provocadas por fallos del traductor, entrada en lazos infinitos, producir resultados erróneos, y detectar sólo el primer error y detenerse. 
- **Aceptables**: Evitar la avalancha de errores (mala recuperación) y, aunque más complejo, informar y reparar el error de forma automática.

## Reparación de errores

>[!def] Detección de error
>El analizador léxico detecta un error cuando no existe transición desde el estado que se encuentra para el símbolo de la entrada. El símbolo de la entrada no es el esperado.


### Estrategias a adoptar

1. **Pasar al estado inicial**, ignorando los símbolos previos al lexema, iniciando de nuevo el proceso de identificación de errores
2. **Proceso de sincronización**, también conocido como *como pánico (panic)*. Consiste en ignorar los símbolos de la entrada no esperados hasta que aparezca un símbolo esperado. Esta estrategia es buena cuando aparecen símbolos extraños de forma extra.
3. **Reparar los errores** mediante transformación de lexemas (borrar caracteres estraños, insertar caracteres que falten, intercambio de caracteres y substitución de caracteres).
