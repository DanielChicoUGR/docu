---
tags:
  - PatronSoftware/Comportamiento
  - "#TODO"
---
Inclusion de un método "plantilla" en una clase abstracta
- Implementa una secuencia de pasos usados por un algoritmo de la clase
- Deja la implementación de cada uno de los métodos concretos a las subclases
Pueden llamar a distintos tipos de operaciones:
- Métodos concretos de la clase concreta
- Métodos implementados en la clase abstracta
- Métodos abstractos de la clase abstracta
- [[Factory Method]]s
- *Hook Methods*. Implementados en la clase abstracta que pueden ser sobrescritos
# Cuando debe utilizarse
- Una clase deba extender únicamente los pasos particulares de un algoritmo
- Muchas clases tienen algoritmos idénticos pero con algunas diferencias mínimas
# Ventajas
- Los clientes pueden sobrescribir solo ciertas partes de un algoritmo grande
- **Reutilización de código**. Código repetido en la subclase
# Diagramas de clase
## General
https://refactoring.guru/images/patterns/diagrams/template-method/structure-2x.png
![[structure-2x 2 1.png]]

## Aplicado
https://refactoring.guru/images/patterns/diagrams/template-method/example-2x.png
![[example-2x 1 1.png]]
# Ejemplo de código
```python
TODO
```