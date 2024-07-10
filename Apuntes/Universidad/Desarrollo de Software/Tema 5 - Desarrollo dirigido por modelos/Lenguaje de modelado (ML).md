Siendo:
- $m$ -> **[[Metamodelo]]** / Sintaxis abstracta
- $n$ -> **Notación** / Sintaxis concreta
	- Sistema de gráficos o símbolos, caracteres y expresiones abreviadas, utilizado en disciplinas artísticas y científicas para representar hechos técnicos y cantidades por convención
- $s$ -> **Semántica**
	- Aspectos del significado, sentido o interpretación de signos lingüísticos
- $p$ -> **Pragmática** / Guías de uso
	- Influencia del contexto en la interpretación del significado
Un ML es el conjunto de todos los posibles modelos que se ajustan a $m$, se representan por $n$, satisfacen $s$ y tienen en $p$ una guía de la forma de uso mas apropiada
![[Pasted image 20240621001000.png]]
## Clasificación
- **GPML (General Purpose Modeling Language)**
	- ==Numero mayor de conceptos generales que invitan a un uso mas amplio en diferentes campos== de aplicación
		- *UML*
		- *SysML* para generar documentación de sistemas software
- **D(S)ML (Domain-Specific Modeling Language)**
	- Usan un ==numero mas reducido de conceptos generales y mas relacionados con el campo especifico== de su dominio de aplicación
	- ==Mas fáciles de entender y de validar, pero con mayor coste== debido al proceso de aprendizaje, implementación y mantenimiento del mismo, además de las herramientas que permiten el desarrollo de software usando dicho lenguaje
## Estructuración
Los ML pueden estructurarse en base a distintos puntos de vista, clasificados en dos criterios
- **Nivel de abstracción (terminología MDA de OMG)**
	- **==Independiente de la computación== (==CIM==)**
	- **==Independiente de la plataforma== (==PIM==)**
	- ==**Especifico de una plataforma== (==PSM==)**
	- **Multiple**: distintos niveles de abstracción (CIM, PIM, PSM)
- **Perspectiva o dimension funcional**
	- **Estático**
		- El lenguaje permite describir el sistema desde una perspectiva funcional ==estructural== (clases, objetos, nodos, bloques, relaciones)
			- *Diagrama UML*
			- *Diagrama de componentes*
	- **Dinámico**
		- El lenguaje permite describir la funcionalidad del sistema en base al ==comportamiento== del mismo (tareas, operaciones, estados, eventos, mensajes y sus relaciones)
			- *Diagramas de actividad*
			- *Maquinas de transición de estados*
			- *Diagramas de procesos de negocio en Business Process Model and Notation (BPMN)*