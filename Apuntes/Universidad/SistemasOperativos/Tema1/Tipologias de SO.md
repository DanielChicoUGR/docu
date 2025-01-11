
## Arquitecturas de un SO

### Monolítico:

El SO es el único programa que se ejecuta en el modo  
más privilegiado del procesador. Las dependencias entre los distintos módulos son complejas salvo para algunos elementos bien establecidos. El modelo de obtención de servicios es la llamada a procedimiento. 

Esta arquitectura tiene varios problemas. La fuerte dependencia entre módulos provoca dificultades a la hora de comprender el código y de modificarlo, y al ser un solo programa en memoria, si un módulo falla puede provocar la caída del sistema.

### Arquitectura de Microkernel

Una parte de la funcionalidad del SO se implementa como kernel y el resto como  interfaz de usuario. Esta arquitectura soporta memoria virtual de bajo nivel, creación de procesos (hebras) y, comunicación y sincronización. 

El modelo de obtención de servicios es por paso de mensajes entre procesos. La 
aplicación solicita un servicio al SO y espera su resolución, el microkernel recibe la solicitud y entrega el mensaje al Server que genera el resultado y lo envía al kernel para que se lo mande a la aplicación.

Es una arquitectura fiable porque la caída de un módulo no implica la caída total del sistema, solo provoca una parcial que puede recuperarse. Es extensible porque podemos añadir más procesos de usuario y servicios. Pero el rendimiento es peor que el de la arquitectura monolítica

## SOs de propósito específico

### SOs de Tiempo Real (RTOS)

Se utilizan para aplicaciones especializadas, debe garantizar la corrección no solo del resultado lógico de la computación sino del tiempo empleado. El problema es su planificabilidad.

Algunos procesos se clasifican como procesos de tiempo real (RT) que tienen como objetivo procesar los eventos que se producen en el sistema de control. Estos eventos ocurren en tiempo real, por lo que los procesos RT tienen un tiempo límite de ejecución

#### Características

- **Determinismo**. Velocidad de respuesta del RTOS frente a interrupciones. 
- **Reactividad**. Tiempo que tarda el RTOS en la RSI. 
- **Control de la prioridad de los procesos RT**. El usuario debe controlar la prioridad de un proceso RT.
- **Fiabilidad**. Debe de tener tolerancia a fallos porque la estabilidad del sistema es crítica.

### SOs para sistemas empotrados (EOS)

Esta especializado para utilizar computadores en sistemas más grandes (coches, teles, GPS, ...). La funcionalidad viene limitada por el sistema empotrado. Su principal característica es la robustez en cuanto a la ejecución de procesos ya que debe lidiar con restricciones de memoria y potencia de cómputo. Normalmente se les conoce como RTOS porque casi todos tienen requisitos de tiempo real.
