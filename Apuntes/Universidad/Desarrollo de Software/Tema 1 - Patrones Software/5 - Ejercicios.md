# Identificar el patron Software
1. Patron que especifique un mecanismo para construir un complejo objeto paso a paso, donde se necesitan diferentes representaciones del objeto para diferentes procesos de pedido en un restaurante online

	*Builder*

2. Desarrolle un marco para juegos que permita extender fácilmente el tipo de personajes disponibles, sin cambiar el código que añade nuevos personajes al juego

	*Factory Method*

3. Construya un sistema de edición de gráficos que debe permitir al usuario crear objetos personalizados y luego duplicarlos sin conocer los detalles de cómo se crean o estructuran

	*Prototype* para duplicación y *Decorator* para personalización

4. Implemente un gestor de configuración para su aplicación que asegure que solo haya una instancia de la configuración en toda la aplicación y que sea accesible globalmente

	*Singleton*

5. Integre una librería de procesamiento de imágenes de terceros en su aplicación de galería, pero la interfaz de la librería no es compatible con el sistema actual de su aplicación

	*Adapter*

6. Desarrolle un sistema de archivos donde archivos y carpetas puedan ser tratados de manera uniforme

	*Composite*

7. Implemente un sistema de pedidos de café donde se pueda añadir dinámicamente nuevos complementos y variantes a los cafés sin alterar las clases existentes

	*Decorator* para los complementos y *Prototype* para poder reutilizar las variantes con complementos

8. Cree una interfaz simple para el complejo sistema de subcomponentes de un home-theater que incluye el proyector, amplificador, reproductor de DVD y las luces de la habitación

	*Facade*

9. Desarrolle un sistema de alertas meteorológicas donde los usuarios puedan recibir actualizaciones en tiempo real cuando se emitan nuevas previsiones

	*Observer*

10. Diseñe un sistema de navegación que pueda calcular la ruta entre dos puntos utilizando diferentes algoritmos de ruta como el más rápido, el más corto y el más económico

	*Strategy*

11. Imagine que es un ingeniero de software encargado de simplificar la interacción de los usuarios con un sistema de reservación de viajes, que incluye múltiples componentes como reservación de vuelos, hoteles y alquiler de autos. Cada uno de estos componentes tiene su propio sistema de interfaz complicado

	*Facade*

# Identificar patron, realizar diagrama UML, escribir código de clases y main()

1. Necesitas diseñar un sistema de gestión de tareas para un equipo de proyecto. Las tareas pueden ser simples o complejas, las ultimas consisten en sub-tareas. Debes permitir que las tareas simples y las tareas compuestas sean tratadas de la misma manera.
	*Composite*
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
2. Estás creando un simulador de tráfico que debe poder a diferentes distancias (euclídea, Manhattan y distancia coseno). El usuario podrá elegir qué distancia ejecutar en tiempo de ejecución para ir desde un punto A a otro punto B
	*Strategy*
	```java
	public class Punto {
		// Por simplicidad los haremos publicos
		public double x;
		public double y;

		Punto(double x, double y) {
			this.x = x;
			this.y = y;
		}

	}
	
	public interface Distancia {
		double calcular(Punto a, Punto b);
	}

	public class DistanciaEuclidea implements Distancia {

		@Override
		double calcular(Punto a, Punto b) {
			// ...
		}

	}

	public class DistanciaManhattan implements Distancia {

		@Override
		double calcular(Punto a, Punto b) {
			// ...
		}

	}

	public class DistanciaCoseno implements Distancia {

		@Override
		double calcular(Punto a, Punto b) {
			// ...
		}

	}

	public class SimuladorTrafico {

		protected Distancia distancia;

		SimuladorTrafico(Distancia distancia) {
			this.distancia = distancia;
		}

		double calcular(Punto a, Punto b) {
			return this.distancia.calcular(a, b);
		}

	}

	public class Ejercicio2 {
		public static void main(String[] args) {
			Distancia d = DistanciaCoseno()
			SimuladorTrafico simulador = SimuladorTrafico(d)
	
			Punto a = new Punto(5, 3);
			Punto b = new Punto(2, 7);
			double distancia = simulador.calcular(a, b);
			System.out.println("Distancia: " + distancia)
		}
	}
	```
3. Una empresa de café desea una aplicación que pueda añadir ingredientes adicionales a una orden de café. Cada adición (leche, azúcar, crema, etc.) agrega un costo adicional y la descripción del café debe actualizarse en consecuencia. La solución debe permitir añadir nuevos ingredientes sin cambiar el código existente de las clases de café
	*Intercepting Filters*
4. Desarrolle una aplicación para personalizar vehículos. Cree la clase base Vehículo con un método costo y descripción. Extienda esta funcionalidad con clases adicionales como `ConGPS`, `ConPinturaEspecial` y `ConAsientosDeLujo` que agreguen comportamientos y costos adicionales. Estas clases deben poder envolver objetos de tipo `Vehiculo` y modificar su comportamiento sin cambiar la clase `Vehiculo` original
	*Decorator*
5. Una aplicación de un blog necesita generar diferentes tipos de publicaciones: Artículo, Noticia, y Entrevista. Cada tipo de publicación tiene un método publicar que difiere en su comportamiento. Diseña un sistema que permita la creación de estas publicaciones sin determinar específicamente la clase de publicación en el código cliente
	*Factory Method*
6. Para un juego de estrategia, se requiere un sistema para crear copias exactas de unidades de combate sin conocer sus clases específicas. Las unidades tienen estados y comportamientos que pueden ser duplicados. Implementa este sistema asegurando que el proceso de duplicación sea eficiente y seguro
	*Prototype* tanto para los personajes como para los comportamientos y estados
7. Un sistema de análisis de datos trabaja con diferentes proveedores de datos. Uno de los proveedores suministra los datos en un formato incompatible con el sistema actual. Implementa una solución que permita al sistema utilizar los datos de este proveedor sin cambiar el código fuente del sistema de análisis
	*Adapter*




