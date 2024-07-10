**Reestructurar** significa realizar cambios en la estructura del software para mejorar su calidad interna, para hacerlo mas fácil de comprender y de mantener, sin cambiar el comportamiento observable del sistema. En lenguajes no OO, la reestructuración se limita al nivel de una función o un bloque de código, en sistemas OO, con lenguajes mucho mas ricos, la reestructuración es mucho mas compleja y se denomina **refactorización**
- Proporciona estabilidad en la arquitectura
- Proporciona legibilidad al código
- Facilita el [[Mantenimiento perfectivo|mantenimiento perfectivo]] y la [[Evolución software|evolución]], flexibilizando las tareas de integración de nuevas funcionalidades del sistema
## Que refactorizar

> [!warning] Hediondez (olor) de codigo
> Sintoma en el codigo que puede indicar la presencia de un problema mas serio.

Aunque un código que "huele" no implica errores, si que tiene mas posibilidades de provocar errores en el futuro o mayor dificultad para hacer cambios, algunos ejemplos son:
- **Código duplicado**. Fuente de errores futuros porque implica doble mantenimiento
- **Larga lista de parámetros**. Los posibles errores vienen de la facilidad para cambiar el orden en las llamadas sin darnos cuenta
- **Métodos grandes**. Difícil de entender, mantener y validar
- **Clases grandes**. Difíciles de mantener
- **Cadenas de mensajes**. Falta algún método o función que permita hacer ese encadenamiento
## Refactorización básica y compleja
La refactorización incluye una serie concreta de actividades básicas, las cuales se pueden combinar para formar refactorizaciones complejas. Las transformaciones básicas son:
- Agregar una clase, método o atributo
- Renombrar una clase, método o atributo
- Mover un atributo o método hacia arriba o hacia abajo en la jerarquía
- Eliminar una clase, método o atributo
- Extraer fragmentos de código en métodos separados