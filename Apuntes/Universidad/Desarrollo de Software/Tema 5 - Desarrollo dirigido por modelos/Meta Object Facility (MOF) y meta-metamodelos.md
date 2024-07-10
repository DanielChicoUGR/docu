En el campo de los [[Lenguaje de modelado (ML)|ML]]: un ejemplo es el estándar **Meta Object Facility (MOF)**, del **núcleo de MDA** (de OMG), el cual ==asigna tipos== (e interfaces para usarlos) ==a las distintas entidades de una arquitectura==

==MOF se define a si mismo usando MOF==

Esta formado por una arquitectura de cuatro capas, capas que se describen a continuación de la mas alta a la mas baja:
- **M3: Meta-metamodelo**. 
	- El lenguaje para especificar metamodelos (modelos M2). **MOF** se crea a si mismo instanciándose de su propio modelo
- **M2: [[Metamodelo]]**. 
	- Instanciados a partir de M3, siendo cada elemento del metamodelo una instancia de un elemento definido en M3
	- Un ejemplo de metamodelo o instancia de MOF es UML o CWM (Common Warehouse Metamodel)
- **M1: [[Modelo]]**. 
	- Definidos según los intereses y necesidades de los usuarios y descritos mediante los metamodelos de M2
	- Ejemplos:
		- Todos los modelos escritos en UML. Un modelo de usuario puede contener tanto elementos de modelo (clases) o instancias de las clases (`:nombreDeInstancia`)
- **M0: Datos**. 
	- Describen los objetos que existen en un entorno de computo concreto o en el mundo real

![[Pasted image 20240620235924.png]]
![[Pasted image 20240621000121.png]]
