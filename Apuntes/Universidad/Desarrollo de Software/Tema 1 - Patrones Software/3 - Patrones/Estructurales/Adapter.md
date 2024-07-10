---
tags:
  - PatronSoftware/Estructural
  - "#TODO"
---
Adaptador, en español

Permite que clases con interfaces incompatibles trabajen juntas, **convirtiendo la interfaz de la clase existente en otra que el cliente espera**.

Es especialmente útil a la hora de **reutilizar código existente sin alterar su estructura** o cuando se diseñan sistemas que deben ser compatibles con futuras implementaciones
Facilita la **interoperabilidad** y promueve la reusabilidad de código, adaptando interfaces sin modificar código fuente existente
Es un patron bastante indicado si queremos usar una gran variedad de subclases ya existentes
# Uso típico
- Integrar clases que no se pueden modificar en un nuevo sistema
- Cuando se prevé la necesidad de intercambiar bibliotecas externas
# Ventajas y desventajas
## Ventajas
- **Flexibilidad**
- **Organización**
- **Integración de clases con diferentes interfaces**
- Principio de responsabilidad única
- Principio de abierto / cerrado
## Desventajas
- **Complejidad**. Hay que introducir nuevas interfaces y clases
- **Rendimiento** (en menor medida)
# Diagrama de clases
Se pueden aplicar en los dos ámbitos
## Ámbito de objeto
Mas indicado si queremos usar una gran variedad de subclases ya existentes
### Ejemplo general
![[structure-object-adapter-2x.png]]
### Ejemplo aplicado
![[example-2x 2 1.png]]
## Ámbito de clase
Requiere herencia multiple
![[structure-class-adapter-2x.png]]
# Ejemplo de código (ámbito de objeto)
```java
TODO
```
