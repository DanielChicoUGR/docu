
Definición de Einstein: Una explicación de los datos de hacerse *Tan simple como sea posible, pero no simple*.

La Navaja de occam es un principio filosófico, que acaba aplicandose como heurística dentro de la tería del aprendizaje.

``` ad-quote
title: Navaja de Occam

El modelo mas simple que se ajusta a los datos es también el mas verosimil
```

## Preguntas extraidas de esta definición:

### ¿Que significa que el modelo sea simple?

#### Como medimos la complegidad? -> Dos tipos:
1. **Complegidad de un objetos** -> de una hipotesis 
	1. MDL (Minimal Descriptions (Lands?)) ->
	2. Orden de Polinomios
2. **Complegidad de un conjunto de objetos**  -> Conjunto de hipotesis
	1. Entropia: 
		- Corres un experimento, consideras todas las posibles soluciones+probabilidades. Generar funcion en base a estos datos que modele el "desorden" de tu modelo
	1. Dimension VC
		- Describe la diversidad del conjunto de hipotesis, mas diverso mas complejo.


Cuando nos referimos a un modelo simple, se piensa en que la hipotesis per sé sea simple. La prueba matemática usa la complegidad del conjunto de hipotesis $H$

#### Como se conectan?
La complegidad de un modelo se puede expresar como $l$ bits que especifican $h$. -> $h$ es uno de los $2^l$ elementos de $H$.
**Ejemplo con valores reales?**
Un polinomio de orden 17 es complejo, oscila bastante, también se  considera complejo ya que existen mas posibles combinaciones con 17 elementos que de polinomios de orden menor.

Esto no quiere decir que si la solución parece compleja no sea la mejor. posiblemente parezca compleja pero se base en una estructura simple que soporte bien los datos será una hipótesis valida (Aplica a SVM (Generar nota de Suport Vector Machine)).


 

### ¿Como sabemos que mas simple es mejor?

