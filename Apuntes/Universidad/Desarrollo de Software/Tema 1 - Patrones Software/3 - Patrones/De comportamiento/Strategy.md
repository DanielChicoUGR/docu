---
tags:
  - PatronSoftware/Comportamiento
  - "#TODO"
---
Define una familia de algoritmos, encapsula cada uno de ellos y los hace intercambiables. Permite que el algoritmo varíe independientemente de los clientes que lo utilizan
# Cuando debe utilizarse
- Cuando hay varias formas de realizar una operación, y se desea elegir entre ellas en tiempo de ejecución
- Cuando se prevé que la lista de algoritmos alternativos pueda ampliarse en el futuro
- Cuando una clase define muchos comportamientos y estos aparecen en sus operaciones como multiples condicionales
- Existen muchas clases similares que solo se diferencian en como realizan una operación
- Aislar la lógica de los detalles de implementación de algoritmos
# Ventajas y desventajas
## Ventajas
- **Flexibilidad**. Facilita el cambio del comportamiento de una instancia de una clase en tiempo de ejecución
- [[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]
- [[1 - Conceptos#Principio de cerrado / abierto|Principio de cerrado / abierto]]. Se pueden implementar nuevos algoritmos fácilmente
## Desventajas
- **Complejidad**. Puede aumentar la complejidad del código al introducir multiples clases y interfaces adicionales
- Los clientes tienen que conocer las diferencias entre las estrategias para poder elegir la adecuada
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/strategy/structure-2x.png
![[structure-2x 1 1.png]]

## Aplicado
https://refactoring.guru/images/patterns/diagrams/strategy/solution-2x.png
![[solution-2x.png]]
# Ejemplo de código
```python
from abc import ABC, abstractmethod

class Ordenacion(ABC):
	@abstractmethod
	def ordenar(self, array): pass

class QuickSort(Ordenacion):
	def ordenar(self, array):
		# ...

class BubbleSort(Ordenacion):
	def ordenar(self, array):
		# ...

class InsertionSort(Ordenacion):
	def ordenar(self, array):
		# ...

##############################################

class Sorter:
	def __init__(strategy):
		self._strategy = strategy

	def ordenar(array):
		self._strategy.ordenar(array)

##############################################

sorter = Sorter(QuickSort())
array_ordenado = sorter.ordenar([4,2,5,1,3])
```