---
tags:
  - PatronSoftware/Creacional
---
Proporciona una interfaz para crear familias de objetos relacionados o dependientes sin especificar sus clases concretas. La creación de los objetos es independiente de su representación

*Por ejemplo, si quisiéramos implementar factorías de muebles de varios estilos cada una, el tipo de factoría sera el tipo de estilo, y ya en esa factoría especificaremos que mueble queremos crear.*
# Cuando debe utilizarse
- El programa debe funcionar con varias familias de productos relacionados, pero no debe depender de las clases concretas de esos productos
- Hay una clase con un grupo de [[Factory Method]]s que nublen su responsabilidad principal
# Uso típico
- Crear bibliotecas o frameworks que necesitan ser extendidos por los usuarios
- Desarrollar aplicaciones que necesitan ser independientes de como se crean los objetos
- Proporcionar una biblioteca de productos, permitiendo implementar nuevos productos sin cambiar el código cliente
# Ventajas y desventajas
## Ventajas
- Separa la creación de objetos y su uso
- Los productos de una fabrica son compatibles entre si
- Evitar un fuerte acoplamiento entre los productos y el cliente
- [[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]. Puede separarse el código para la creación de objetos.
- [[1 - Conceptos#Principio de cerrado / abierto|Principio de cerrado / abierto]]. Pueden incluirse nuevos productos con facilidad
## Desventaja
- Mayor complejidad
# Relaciones con otros patrones
- Evoluciona desde [[Factory Method]]
- Abstract Factory devuelve el producto inmediatamente, mientras que _[[Builder]]_ te permite ejecutar algunos pasos adicionales de construcción antes de extraer el producto
- **Se puede utilizar *[[Factory Method]]* y *[[Prototype]]* para escribir los métodos**
- Alternativa a *[[Facade]]* si se desea esconder la forma en la que se crean los objetos
- Se puede implementar como *[[Singleton]]*
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/abstract-factory/structure-2x.png
![[structure-2x.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/abstract-factory/example-2x.png
![[example-2x.png]]
# Ejemplos de código
## Python
```python
from abc import ABC, abstractmethod

class Coffee(ABC):
	@abstractmethod
	def serve(self): pass

class Espresso(Coffee):
	def serve(self): return "Serving an Espresso"

class Capuccino(Coffee):
	def serve(self): return "Serving an Capuccino"

class CoffeeFactory(ABC):
	@abstractmethod
	def create_coffee(self): pass

class EspressoFactory(CoffeeFactory):
	def create_coffee(self): return Espresso()

class CapuccinoFactory(CoffeeFactory):
	def create_coffee(self): return Capuccino()

factory = EspressoFactory()
coffee = factory.create_coffee()
print(coffee.serve()) # Serving an Espresso
```
## Java
```java
public interface Coffee { String serve(); }

public class Espresso implements Coffee {
	public String serve() { return "Serving an Espresso"; }
}

public class Cappuccino implements Coffee {
	public String serve() { return "Serving a Cappuccino"; }
}

public interface CoffeeFactory {
	CoffeeFactory createCoffee();
}

public class EspressoFactory implements CoffeeFactory {
	public Coffee createCoffee() { return new Espresso(); }
}

public class CappuccinoFactory implements CoffeeFactory {
	public Coffee createCoffee() { return new Cappuccino(); }
}

CoffeeFactory factory = new EspressoFactory();
Coffee coffee = factory.createCoffee();
System.out.println(coffee.serve()); // Serving an Espresso
```
