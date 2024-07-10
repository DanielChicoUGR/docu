---
tags:
  - PatronSoftware/Comportamiento
  - "#TODO"
---
Tambien conocido como *Dependientes* o *Publicar-Subscribir*
Multiples observadores responden a los cambios en un sujeto observable
Esencial en diseño de sistemas flexibles y poco acoplados
El sujeto solo conoce una interfaz para notificar a los observadores
- **Comunicación indirecta** entre sujeto y observadores
- **Notificación inmediata** a los observadores cuando hay un cambio en el sujeto
- **Flexibilidad**. Nuevos observadores pueden suscribirse en cualquier momento
# Cuando debe utilizarse
- Los cambios en el estado de un objeto necesitan cambiar otros objetos y el grupo de objetos sea desconocido o cambie en tiempo de ejecución
- Algunos objetos de tu aplicación deben observar a otros pero solo durante un tiempo limitado o en casos específicos
# Ventajas y desventajas
## Ventajas
- **Desacoplamiento**. Los sujetos operan independientemente de los observadores, mejorando la mantenibilidad
- **Escalabilidad**. Es sencillo agregar o eliminar observadores
- [[1 - Conceptos#Principio de cerrado / abierto|Principio de cerrado / abierto]]
- **Permite establecer relaciones entre objetos en tiempo de ejecución**
## Desventajas
- **Posible sobrecarga**. Debido a un volumen alto de notificaciones
- **Gestion compleja**. A la hora de gestionar las subscripciones y notificaciones
- **Orden aleatorio de las notificaciones**
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/observer/structure-2x.png
![[structure-2x 3.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/observer/example-2x.png
![[99 - Adjuntos/Imagenes/example-2x 2.png]]
# Ejemplo de código
```python
from abc import ABC, abstractmethod

class TemperatureObserver(ABC):
	@abstractmethod
	def update(self, temperature: float):
		pass

class Subject(ABC):
	@abstractmethod
	def register_observer(self, observer):
		pass
		
	@abstractmethod
	def remove_observer(self, observer):
		pass

	@abstractmethod
	def notify_observers(self):
		pass

######################################################

class TemperatureSensor(Subject):
	def __init__(self):
		self._observers = []
		self._temperature = 0.0

	def set_temperature(self, temperature):
		self._temperature = temperature
		self.notify_observers()

	def register_observer(self, observer):
		self._observers.append(observer)

	def remove_observer(self, observer):
		self._observers.remove(observer)

	def notify_observers(self):
		for observer in this._observers:
			observer.update(self._temperature)

#######################################################

class TemperatureDisplay(TemperatureObserver):
	def update(self, temperature):
		print(f"Display: temperature is now {temperature}")

class TemperatureAlertSystem(TemperatureObserver):
	def update(self, temperature):
		if temperature > 30:
			print(f"Alert: temperature is above 30")

#######################################################

sensor = TemperatureSensor()
display = TemperatureDisplay()
alert_system = TemperatureAlertSystem()

sensor.register_observer(display)
sensor.register_observer(alert_system)

sensor.set_temperature(25)
sensor.set_temperature(30)
sensor.set_temperature(35)
```