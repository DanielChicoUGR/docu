Regula los movimientos del robot de acuerdo a la tarea a realizar y a la información recibida de los sensores.

Eventualmente puede comunicarse con otros dispositivos para realizar una tarea de forma conjunta

**Se clasifican en :**
- *Control en bucle abierto*:
	- Simple y económico
	- Propenso a errores
- *Control en bucle cerrado*:
	- Durante el movimiento compara la posición real (sensores) con la deseada
	- Adapta órdenes para reducir el error de posicionamiento
	- Imprescindible en aplicaciones que requieren precisión

Existen varios grados de control que son función del tipo de prámetros que se regulan, lo que da lugar a los siguientes tipos de controladores:
?
1. De posición $\rightarrow$ interviene únicamente en el control de la posición del efector
2. Cinemático $\rightarrow$ El control se realiza sobre la posición y la velocidad
3. Dinámico $\rightarrow$ Además de regular posición y velocidad, controla las propiedades diámicas del manipulador y de los elementos asociados a él.
4. Adaptativo $\rightarrow$ Engloba todas las regulaciones anteriores y, además, controla la variación de las características del manipulador al variar la posición
<!--SR:!2023-05-10,3,250-->

En función del tipo de sistema de control, los robots del mercado se pueden clasificar en:

# Robot De Secuencia Limitada (el Más sencillo)
- Las posiciones relativas de las articulaciones se controlan por ==interruptores o topes mecánicos con fin de carrera== para establecer los puntos finales de desplazamiento de cada articulación.
- Para estableces las posiciones y secuencias de topes *se lleva a cabo una puesta a punto mecánica del robot en vez de una programación* 
- La ==secuencia de movimientos== se define mediante un conmutador paso a paso u otro dispositivo de secuenciación
- Se suelen usar en tareas de coger y situar
- Son simples pero costosos
<!--SR:!2023-05-10,3,250!2023-05-09,1,210-->

# Robot De Reproducción Con Control
- Tienen una unidad de control mas sofisticada
- Se le señalan al robot (==proceso de programación==) una serie de movimientos y posiciones que son almacenados en la memoria y luego repetidos por el robot bajo su propio control
- Suelen tener alguna forma de servocontrol y sistemas de realimentación en bucle cerrado
<!--SR:!2023-05-10,3,250-->

## Robot Punto a Punto.
- Realizan ciclos de movimientos que consisten en una seria de localizaciones de puntos deseados y acciones afines.
- No controlan la trayectoria tomada por el robot para cambiar de un punto a otro.
- Apropiados para máquinas de carga y descarga y de soldadura por puntos entre otros.

## Robot De Trayectoria Continua.
- Realizan ciclos de movimiento en los que se controla la trayectoria seguida por el robot
- El robot se desplaza a través de serie de puntos próximos, que describen la trayectoria deseada
- Apropiados para aplicaciones como revestimiento por pulverización y soldadura.


# Robot Inteligente (el Mas sofisticado)
- Tienen la capacidad para reproducir un ciclo de movimiento programado y además para interaccionar con el entorno, modificando su ciclo de trabajo programado en respuesta a las condiciones particulares que se produzcan en el lugar de trabajol
- Toman decisiones lógicas basados en los datos recibidos de los sensores externos.
- El sistema de control es más complejo y requiere de mayor capacidad de cómputo.

