---
tags:
  - PatronSoftware/Creacional
---
Proporciona una interfaz para crear objetos en una superclase, pero permite a las subclases cambiar el tipo de objetos que serán creados
# Uso típico
- Cuando no se pueda anticipar el tipo de objetos que debe crear
- La clase quiere que sus subclases especifiquen los objetos que crea
- Las clases delegan responsabilidades a una de varias subclases auxiliares y se planea localizar el conocimiento de cual subclase auxiliar es la delegada
- Los usuarios pueden extender los componentes internos de tu biblioteca o framework
- Reutilización de objetos para ahorrar recursos del sistema
# Ventajas y desventajas
## Ventajas
- Reduce el acoplamiento entre el creador y los productos
- [[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]
- [[1 - Conceptos#Principio de cerrado / abierto|Principio de cerrado / abierto]]. Delega la responsabilidad de instanciación de objeto a las subclases 
- *Principio de Inversion de Dependencia*
- Facilita la adición de nuevas variantes de productos sin alterar el código cliente existente, promoviendo la escalabilidad y mantenibilidad
## Desventajas
- Mayor complejidad
# Relacion con otros patrones:
- Puede evolucionar hacia *[[Abstract Factory]]*, *[[Prototype]]* o *[[Builder]]*
- Las clases a menudo se basan en [[Factory Method]]s, pero también se puede utilizar [[Prototype]]
- No requiere un paso de inicialización
- Especialización y a su vez un gran paso del [[Template Method]]
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/factory-method/structure-2x.png
![[structure-2x 1.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/factory-method/example-2x.png
![[example-2x 1.png]]
# Ejemplos de código
## Python
```python
class Coffee:
	def __init__(self, size='medium', milk='none', insensity='regular'):
		self.size = size
		self.milk = milk
		self.intensity = intensity
		
	def serve(self):
		description = f'{self.size} {self.intensity}'
		if self.milk != 'none':
			description += f' with {self.milk} milk'
		return f'Serving a cup of {description} coffee'

class Espresso(Coffee):
	def __init__(self, milk='none'):
		super().__init__(size='small', intensity='strong', milk=milk)

class Cappuccino(Coffee):
	def __init__(self, size='medium', intensity='regular'):
		super().__init__(size=size, milk='whole', intensity=intensity)

class Americano(Coffee):
	def __init__(self, size='large', intensity='light'):
		super().__init__(size=size, milk='none', intensity=intensity)

####################################################################################

class CoffeeFactory:
	def get_coffee(self, coffee_type, size='medium', milk='none', intensity='regular'):
		if coffee_type == 'espresso':
			return Espresso(milk=milk)
		elif coffee_type == 'cappuccino':
			return Cappuccino(size=size, intensity=intensity)
		elif coffee_type == 'americano':
			return Americano(size=size, intensity=intensity)
		else:
			return ValueError("Incorrect coffee type")

####################################################################################

factory = CoffeeFactory()

espresso = factory.get_coffee('espresso')
print(espresso.serve())

capuccino = factory.get_coffee('capuccino')
print(espresso.serve())

americano = factory.get_coffee('americano')
print(americano.serve())
```

## Java
```java
public abstract Coffee {

	protected String size, milk, intensity;
	
	public abstract String serve();
	
}

public class Espresso extends Coffee {

	public Espresso() {
		size = "small";
		milk = "none";
		intensity = "strong";
	}

	@Override
	public String serve() {
		return "Serving a " + size + " espresso with " + intensity + " intensity";
	}

}

public class Capuccino extends Coffee {

	public Capuccino() {
		size = "medium";
		milk = "whole";
		intensity = "regular";
	}

	@Override
	public String serve() {
		return "Serving a " + size + " capuccino with " + milk + " milk";
	}

}

public class CoffeeFactory {

	public static Coffee getCoffee(String coffeeType) {
		switch (coffeeType) {
			case "espresso":
				return new Espresso();
			case "capuccino":
				return new Capuccino();
			default:
				throw new IllegalArgumentException("Unknown coffee");
		}
	}

}

// ########################################################################

CoffeeFactory factory = new CoffeeFactory();

Espresso espresso = factory.getCoffee('espresso');
System.out.println(espresso.serve());

// ...
```