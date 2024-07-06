---
tags:
  - PatronSoftware/Creacional
  - "#TODO"
---
Diseñado para la construcción de **objetos complejos**
Separa la construcción de un objeto complejo de su representación, permitiendo el mismo proceso de construcción para crear diversas representaciones

Encapsula la creación y montaje de las partes de un objeto complejo en un director y un constructor concreto, respectivamente.
Oculta los detalles de construcción del objeto y expone solo los pasos necesarios para construir el objeto.

El **constructor** se encarga de agregar los componentes al objeto mientras que el **director** le dice a los constructores como deben hacerlo (orden y modo)
# Uso típico
- Evitar constructores con demasiados parámetros
- En la creación de objetos complejos con multiples partes y configuraciones variadas.
- Cuando se desea una abstracción entre el proceso de construcción de un objeto y su representación final.
- Ejemplos típicos incluyen la construcción de documentos complejos (como documentos HTML o PDF) o la configuración de objetos de un videojuego.
- Construcción de arboles junto con el patron *Composite* u otros objetos complejos
# Ventajas y desventajas
## Ventajas
- [[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]
## Desventajas
- Mayor complejidad
# Relacion con otros patrones

# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/builder/structure-2x.png
![[structure-2x 2.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/builder/example-es-2x.png
![[example-es-2x.png]]

# Ejemplo de código
```python
from abc import ABC, abstractmethod

class ComputerBuilder(ABC):
	def __init__(self):
		self.computer = None

	def create_new_computer(self):
		self.computer = Computer()

	@abstractmethod
	def add_processor(self): pass

	@abstractmethod
	def add_memory(self): pass

	@abstractmethod
	def add_disk(self): pass

	@abstractmethod
	def add_graphics_card(self): pass

########################################################

class GamingComputerBuilder(ComputerBuilder):

	def add_processor(self):
		self.computer.processor = "Intel i9"

	def add_memory(self):
		self.computer.memory = "32GB"

	def add_disk(self):
		self.computer.disk = "1TB SSD"
	
	def add_graphics_card(self):
		self.computer.graphics_card = "NVIDIA RTX 3080"

class OfficeComputerBuilder(ComputerBuilder):

	def add_processor(self):
		self.computer.processor = "Intel i5"

	def add_memory(self):
		self.computer.memory = "16GB"

	def add_disk(self):
		self.computer.disk = "500GB SSD"
	
	def add_graphics_card(self):
		self.computer.graphics_card = "Integrated"

########################################################

class Director:
	def __init__(self, builder):
		self._builder = builder

	def build_computer(self):
		self._builder.create_new_computer()
		self._builder.add_processor()
		self._builder.add_memory()
		self._builder.add_disk()
		if hasattr(self._builder, 'add_graphics_card'):
			self._builder.add_graphics_card()

########################################################

gaming_builder = GamingComputerBuilder()
director = Director(gaming_builder)
director.build_computer()
print(gaming_builder.computer)
```



