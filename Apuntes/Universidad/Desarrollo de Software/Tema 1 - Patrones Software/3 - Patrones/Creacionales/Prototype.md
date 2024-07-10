---
tags:
  - PatronSoftware/Creacional
  - "#TODO"
---
Utiliza prototipos o métodos de clonación para crear objetos
Evita la necesidad de subclases que crean objetos
Permite la adición o eliminación de objetos en tiempo de ejecución

Se puede implementar adicionalmente un **registro de prototipos**
Se podrán agregar prototipos al registro y obtenerlos desde ahi
# Cuando debe utilizarse
- El código no debe depender de las clases concretas de objetos que se necesite copiar
- Se necesite reducir la cantidad de subclases que solo se diferencian en como se inicializan
# Ventajas y desventajas
## Ventajas 
- **Flexibilidad**. Los objetos pueden ser clonados para crear otros similares
- **Menor acoplamiento**. No depende de jerarquías de clases concretas
- **Optimización de rendimiento y recursos**. Cuando la creación es mas costosa que la clonación
## Inconvenientes
- **Complejidad**. Requiere la implementación de clonación
- **Problemas con la clonación profunda**. La clonación superficial puede ser insuficiente para objetos complejos.
# Relacion con otros patrones
# Diagrama de clases
https://refactoring.guru/images/patterns/diagrams/prototype/structure-prototype-cache-2x.png
![[structure-prototype-cache-2x.png]]
# Ejemplo de código
```java
public class HumanDNA implements Cloneable {

	private List<String> geneticCode;

	public HumanDNA() {
		this.geneticCode = new ArrayList<>();
	}

	@Override
	protected HumanDNA clone() {
		try {
			HumanDNA copy = (HumanDNA) super.clone();
			copy.geneticCode = new ArrayList<>(this.geneticCode);
			return copy;
		} catch (CloneNotSupportedException e) {
			throw new AssertionError();
		}
	}

	public void mutateGeneticCode(String mutation) {
		this.geneticCode.add(mutation);
	}

	public String toString() {
		return "Genetic code: " + this.geneticCode;
	}

}

// ##################################################################

HumanDNA originalDNA = new HumanDNA();
HumanDNA assignedDNA = originalDNA;
HumanDNA clonedDNA = originalDNA.clone();

originalDNA.mutateGeneticCode("AGT");
clonedDNA.mutateGeneticCode("CTA");

System.out.println(originalDNA); // AGT
System.out.println(assignedDNA); // AGT
System.out.println(clonedDNA);   // CTA
```