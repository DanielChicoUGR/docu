---
tags:
  - PatronSoftware/Estructural
  - "#TODO"
---
Permite **tratar a objetos simples y compuestos de la misma forma**, mediante una interfaz común que define las operaciones de los compuestos
Permite representar **jerarquías en forma de árbol**
Facilita a los clientes tratar objetos compuestos y simples de manera uniforme

Tenemos como ejemplo un sistema de ficheros con ficheros y directorios, los directorios contienen otros ficheros y directorios (otros elementos del sistema de archivos)
# Ventajas y desventajas
## Ventajas
- **Claridad** de estructura
- **Flexibilidad**. Permite modificar la estructura de objetos compuestos en tiempo de ejecución
- **Simplicidad** para los clientes. Los clientes pueden tratar objetos simples y compuestos de la misma manera
- [[1 - Conceptos#Principio de cerrado / abierto|Principio de cerrado / abierto]]. Se pueden introducir nuevos tipos de elemento sin descomponer el código existente
## Desventajas
- **Dificultad en la restricción de los componentes**. No es fácil restringir los tipos de componentes en una composición
- **Potencial de sobrecarga**. Usar este patron para sistemas muy simples puede resultar en mas código del necesario
# Relacion con otros patrones
- Se puede utilizar *Builder* para la creación de arboles Composite
- Diagrama de clases parecido a *Decorator* ya que ambos se basan en la composición recursiva
	- Se puede utilizar Decorator en clases que implementen Composite
	- Los diseños que utilizan ambos patrones pueden beneficiarse de *Prototype* debido a su capacidad de clonar estructuras complejas
# Diagrama de clases
## General
https://refactoring.guru/images/patterns/diagrams/composite/structure-es-2x.png
![[structure-es-2x 1.png]]
## Aplicado
https://refactoring.guru/images/patterns/diagrams/composite/example-2x.png
![[example-2x 3.png]]
# Ejemplo de código
```java
interface Tarea {
	// ...
	void mostrar();

}

public class TareaSimple implements Tarea {

	protected String nombreTarea;

	TareaSimple(String nombreTarea) {
		this.nombreTarea = nombreTarea;
	}

	@Override
	void mostrar() {
		System.out.println("Tarea simple: " + this.nombreTarea)
	}

}

public class TareaCompuesta implements Tarea {

	protected String nombreTarea;
	List<Tarea> subTareas;
	
	TareaCompuesta(String nombreTarea) {
		this.nombreTarea = nombreTarea;
		this.subTareas = new ArrayList<>();
	}

	void aniadirTarea(Tarea tarea) {
		this.subTareas.append(tarea);
	}

	void eliminarTarea(Tarea tarea) {
		this.subTareas.remove(tarea);
	}

	Tarea obtenerTarea(int indice) {
		return this.subTareas.get(indice);
	}

	void mostrar() {
		System.out.println("Tarea compuesta: " + this.nombreTarea);
		for (Tarea t : this.subTareas) {
			t.mostrar();
		}
	}

}

public class Ejercicio1 {
	public static void main(String[] args) {
		Tarea t1 = new TareaSimple("Mi tarea simple");
		Tarea t2 = new TareaCompuesta("Mi tarea compuesta");
		t2.aniadirTarea(t1);
		t2.mostrar();
	}
}
```
