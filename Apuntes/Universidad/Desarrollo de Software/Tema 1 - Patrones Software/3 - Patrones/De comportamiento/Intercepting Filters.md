---
tags:
  - PatronSoftware/Comportamiento
  - "#TODO"
---
# Características
- Incorpora servicios de forma transparente mediante intercepciones automáticas
- Utiliza una estructura de [[4 - Estilos arquitectónicos#Flujo de datos. Tubería y filtro|tuberia y filtro]] para procesar los datos secuencialmente
- Permite el pre-procesamiento y post-procesamiento de peticiones y respuestas
# Entidades
## Objetivo
Objeto que sera interceptado por los filtros
## Filtro
Interfaz que declara el método abstracto `ejecutar`. Se ejecutaran antes que el objetivo
## Cliente
Envia la peticion a la instancia de Objetivo a traves de un gestor de filtros que envia a su vez la peticion a la cadena de filtros
## Cadena de filtros
Tiene la lista con los filtros a aplicar, ejecutandose en el orden en el que son introducidos. Tras ejecutar los filtros se ejecuta el objetivo
## Gestor de filtros
Gestiona la cadena de filtros
- Crea la cadena de filtros
- Agrega filtros a la cadena
- Solicita que se ejecute
# Ventajas y desventajas
## Ventajas
- Facilita la separación de preocupaciones mediante la modularización de tareas de procesamiento
- Mejora la reutilización de código al permitir la combinación de filtros
- Incrementa la flexibilidad para añadir o modificar comportamientos sin alterar el flujo principal
## Desventajas
- **Complejidad**. En flujos de procesamiento grandes
- **Depuración y rastreo mas difícil**.
- **Bajada de rendimiento**. Por numero de filtros o filtros exhaustivos
# Diagrama de clases
![[fil.png]]
# Ejemplo de codigo
```java
TODO
```