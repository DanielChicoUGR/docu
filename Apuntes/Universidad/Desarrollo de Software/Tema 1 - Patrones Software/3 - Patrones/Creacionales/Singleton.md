---
tags:
  - PatronSoftware/Creacional
  - "#TODO"
---
Resuelve dos problemas:
- **Asegura que una clase tenga una única instancia estática**
- **Proporciona un punto de acceso global a la instancia**
# Cuando debe utilizarse
- Una clase solo debe de tener una única instancia disponible
- Controlar variables globales
# Usos típicos
- Manejar conexiones a bases de datos
- Gestionar configuraciones del sistema
- Aplicar limites de recursos a través de una única instancia controlada
# Ventajas y desventajas
## Ventajas
*TODO*
## Desventajas
- Vulnera el ~~[[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]~~: Resuelve dos problemas al mismo tiempo
- Puede enmascarar un mal diseño. Por ejemplo, cuando los componentes saben demasiado entre ellos
- Requiere un tratamiento especial en programas multihilo
- Puede ser complicado realizar pruebas de despliegue
# Relaciones con otros patrones:
- [[Abstract Factory]], [[Builder]] y [[Prototype]] pueden implementarse como singletons
- Una [[Facade]] puede transformarse a un Singleton
# Diagrama de clases
https://refactoring.guru/images/patterns/diagrams/singleton/structure-es-2x.png
![[structure-es-2x.png]]
# Ejemplo de código
## Python
```python
class CoffeeMachine:
	_instance = None

	def __new__(cls, *args, **kwargs):
		if cls.instance is None:
			cls._instance = super().__new__(cls)
		return cls._instance

	def __init__(self, coffee_type):
		if not hasattr(self, "initialized"):
			self.coffee_type = coffee_type
			self.initialized = True

	def brew(self):
		return f"Brewing a {self.coffee_type}"

##########################################################3

machine1 = CoffeeMachine("latte")
machine2 = CoffeeMachine("espresso")

print(machine1.brew())      # Brewing a latte
print(machine2.brew())      # Brewing a latte
print(machine1 is machine2) # True
```
## Java
```java
public class CoffeeMachine {

	private static CoffeeMachine instance;
	private String coffeeType;

	private CoffeeMachine(String coffeeType) {
		this.coffeeType = coffeeType;
	}

	public static CoffeeMachine getInstance(String coffeeType) {
		if (instance == null) {
			instance = new CoffeeMachine(coffeeType);
		}
		return instance;
	}

	public String prepare() {
		return "Preparing a " + coffeeType;
	}

}

// #################################################################

CoffeeMachine machine1 = CoffeeMachine.getInstance("latte")
Coffeemachine machine2 = CoffeeMachine.getInstance("espresso")

System.out.println(machine1 == machine2); // True
System.out.println(machine1.prepare());   // Preparing a latte
```