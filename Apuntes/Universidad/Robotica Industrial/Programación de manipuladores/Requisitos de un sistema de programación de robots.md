# Entorno De Desarrollo
Se usa de manera extendida lenguajes interpretados con el objetivo de facilitar su depuración

Tendencia a usar como entorno un SO de propósito general

## Características Buscadas En Un SO
1. *Multitarea* $\rightarrow$ Permiten el uso simultáneo y sincronizado del robot y otros sistemas o de varios robots a la vez
2. *Interfáz gráfica* $\rightarrow$ Facilitan el desarrollo.

# Modelado Del Entorno
Se refiere a la representación que tiene el robot de los objetos con los que interacciona. Los objetos se representan mediante sus características geométricas (posición, orientación, dimensiones...)

Para codificar la posición y orientación se suele asignar una trama (Sistema de coordenadas) a cada objeto.
Algunos modelos del entorno permiten establecer relaciones entre objetos.

# Tipos De Datos
Un sistema de programación de robots cuenta con tipos de datos específicos, ademas de los convencionales.

Los tipos de datos específicos permiten representar posiciones y orientaciones.

# Manejo De entradas/salidas

Debe proporcionar métodos para gestionar el E/S. Estas permiten la comunicación con el entorno.

- Entradas $\rightarrow$ El robot puede leerlas y controlar el flujo del programa en función de su valor.
- Salidas $\rightarrow$ El robot posee instrucciones de activación o desactivación de las mismas (suelen ser binarias).

# Comunicaciones
La comunicación del robot puede realizarse usando las entradas/salidas aunque con algunas limitaciones

La mayor parte de los robots industriales de nueva generación disponen disponen de vías de comunicación basadas en estándares.

Algunos fabricantes usan un sistema de control basado en una arquitectura de tipo PC Industrial, que permite adaptarse a nuevos standares de comunicación de manera flexible.

# Control Del Movimiento Del Robot
Un sistema de programación de robots debe incluir la posibilidad de especificar el movimiento del robot. Además de seguir las rutas planificadas por el planificador de trayectorias debe ser capaz de adaptarlas según la información recibida de los sensores.

La consideración de las señales captadas por los sensores puede hacerse a varios niveles:
1. Movimiento protegido $\rightarrow$ Interrupción del movimiento al verificarse alguna condición. Se implementa mediante interrupciones
2. Movimiento acomodaticio $\rightarrow$ Modificación del movimiento según información externa, Se implementa mediante instrucciones específicas.


# Control Del Flujo De Ejecución Del Programa

Un lenguaje de programación de robots ha de permitir al programador especificar de alguna manera un flujo de ejecución de operaciones.
Tienen sintaxis similares a los **LP** convencionales
Suelen implementar de una manera sencilla el paralelismo.