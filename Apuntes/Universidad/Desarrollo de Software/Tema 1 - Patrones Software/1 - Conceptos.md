# Que es un patron Software
Es una solución a un problema habitual que surge en el Desarrollo de Software
Surgen desde la POO y se expanden hasta cualquier paradigma de programación:
- Patrones de diseño
- Patrones arquitectónicos
- Patrones de código (idioms)
## Idioms
```python
# Apertura de ficheros
with open('file.txt', 'r') as f:
	contents = f.read()
```

```python
# Numero de parametros flexible
def func(*args, **kwargs):
	print(args)
	print(kwargs)
```

```python
# Comprension de listas, por simplicidad
squares = [x**2 for x in range(10)]
```

```java
try (FileReader fr = new FileReader("file.txt")) {
	// leer archivo
} catch (IOException e) {
	e.printStackTrace();
}
```

# Diferencias entre `abstract` e `interface` en Java
- `abstract` puede tener métodos implementados, pero `interface` solo puede tener métodos abstractos
- Una clase puede implementar multiples `interface`s, pero solo puede extender una clase `abstract`
- Las `interface`s son útiles para definir contratos comunes, mientras que las clases abstractas son mejores para compartir código
#### `interface`
```java
public interface ProductFactory {
	Product createProduct();
}
```

```java
// Ejemplo interface
public interface Animal {
	void eat();
}

class Dog implements Animal {
	public void eat() {
		System.out.println("I'm eating dog's food.");
	}

	public static void main(String[] args) {
		Dog luca = new Dog();
		luca.eat(); // I'm eating dog's food.
	}
}
```

#### `abstract`
```java
public abstract class ProductFactory {
	protected abstract Product createProduct();
	
	public void seeCommonUtilityMethod() {
		// Con codigo
	}
}
```

```java
// Ejemplo abstract
public abstract Animal {
	public abstract void eat();
	public void sleep() {
		System.out.println("I'm sleeping");
	}
}

class Dog extends Animal {
	// El hijo implementa el metodo abstracto del padre
	public void eat() {
		System.out.println("I'm eating dog's food.");
	}

	public static void main(String[] args) {
		Dog luca = new Dog();
		luca.eat(); // I'm eating dog's food.
		luca.sleep(); // I'm sleeping
	}
}
```
# Diferencias entre `__new__` e `__init__` en Python
*TODO*
# Asignación vs Clonación
Al asignar un objeto ya creado a una variable, guardara una referencia a ese objeto sin copiarlo, de manera que podemos modificar el objeto original desde la referencia. Si quisiéramos modificar el original, tendremos que hacer una clonación de ese objeto, por ejemplo, haciendo uso del patron *Prototype*
# Criterios de calidad
#### Bajo acoplamiento
Pocas dependencias entre clases pertenecientes a subsistemas distintos
#### Alta cohesion
Muchas dependencias entre clases pertenecientes al mismo subsistema
# Principios
## Principio de responsabilidad única
Un patron debe resolver **un problema a la vez**
## Principio de cerrado / abierto
Las clases deben de estar **abiertas para su extension** pero **cerradas para su modificación**
## Principio de inversion de dependencias
Las clases de un sistema deben **depender de las abstracciones** y no de las implementaciones concretas

