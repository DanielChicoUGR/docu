---
tags:
  - PatronSoftware/Estructural
  - "#TODO"
---
Permite **agregar nuevas funcionalidades** a objetos de manera dinámica envolviéndolos en clases decoradoras **sin modificar el código** de las clases existentes

Ofrece una alternativa flexible a la herencia para extender capacidades o para entender el comportamiento de un objeto en tiempo de ejecución
**Envuelve** el objeto
# Ventajas y desventajas
## Ventajas:
- **Flexibilidad**. Los decoradores pueden añadirse o quitarse en tiempo de ejecución para ajustar el comportamiento de los objetos según sea necesario
- **Extensibilidad**. Facilita la adición de nuevas funcionalidades sin modificar el código existente
- **Aplicación selectiva**. Las funcionalidades pueden ser añadidas a objetos específicos sin afectar a otros objetos de la misma clase
- [[1 - Conceptos#Principio de responsabilidad única|Principio de responsabilidad única]]. Se pueden separar las variantes de decoradores en distintos archivos
## Desventajas
- Dificultad para eliminar un decorador especifico de una pila de decoradores
- Dificultad para implementar un decorador independiente de la pila de decoradores
- El código para configurar las capas puede ser "feo"
# Relacion con otros patrones
- *[[Adapter]]* proporciona una interfaz diferente para acceder a un objeto existente, pero con este patron, permanece igual o se amplia
- Diagrama de clases parecido a *[[Composite]]* ya que ambos se basan en la composición recursiva
	- Se puede utilizar *[[Decorator]]* en clases que implementen *[[Composite]]*
	- Los diseños que utilizan ambos patrones pueden beneficiarse de *[[Prototype]]* debido a su capacidad de clonar estructuras complejas
- *[[Decorator]]* te permite cambiar la piel de un objeto, mientras que *[[Strategy]]* te permite cambiar sus entrañas
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/decorator/structure-2x.png
![[structure-2x 4.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/decorator/example-2x.png
![[example-2x 1 2.png]]

# Ejemplo de código
```java
public interface Cafe {
	String descripcion();
}

public class CafeSimple implements Cafe {

	@Override
	String descripcion() {
		return "Cafe";
	}

}

public class DecoradorCafe implements Cafe {

	protected Cafe envuelto;

	DecoradorCafe(Cafe cafe) {
		this.envuelto = cafe;
	}

	@Override
	String descripcion() {
		return this.envuelto.descripcion();
	}

}

public class DecoradorAzucar implements Cafe {

	@Override
	String descripcion() {
		System.out.println(this.envuelto.descripcion() + " con azucar");
	}

}

public class DecoradorLeche implements Cafe {

	@Override
	String descripcion() {
		System.out.println(this.envuelto.descripcion() + " con leche");
	}

}

public class DecoradorCrema implements Cafe {

	@Override
	String descripcion() {
		System.out.println(this.envuelto.descripcion() + " con crema");
	}

}

public class Ejercicio3 {
	public static void main(String[] args) {
		Cafe cafe = new CafeSimple();
		Cafe azucar = new DecoradorAzucar(cafe);
		Cafe crema = new DecoradorCrema(azucar);
		System.out.println(crema.descripcion());
	}
}
```