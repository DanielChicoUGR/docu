- **La [[Mantener el software bajo control|prueba exhaustiva]] no es posible**
- **Probar un programa es tratar que falle**. 
	- Una prueba que no encuentre errores no significa que no los tenga.
- **Prueba temprana**. 
	- Los equipos de prueba no tienen que esperar a que el software esté disponible, cuando antes empiecen, mejor respuesta tendrán ante presiones por posible falta de tiempo. Los tests de [[Validación]] se pueden diseñar en cuanto se completen las especificaciones de requerimientos. Además se pueden hacer [[Prueba estática|tests estáticos]] para revisar las posibles ambigüedades o errores en dichas especificaciones, que evitarán pasar a desarrollar código erróneo. *Cuanto mas tiempo pase, mas costara arreglar los errores*
	![[Drawing 2024-06-19 13.50.38.excalidraw.svg]]
- **Agrupación de defectos**. 
	- Suele ocurrir que los errores no se distribuyen de forma homogénea por todo el código sino que se concentran en unos pocos módulos, por razones de:
		1. Complejidad del sistema 
		2. Código volátil
		3. Efectos de volver a cambiar código
		4. Inexperiencia del equipo de desarrollo
		Sin embargo, las pruebas deben contemplar también el resto de los módulos
- **Prueba de repetición y prueba retroactiva**. 
	- Las pruebas de repetición, pretenden evitar que errores ya corregidos vuelvan a aparecer por nuevos cambios hechos: *Any failed execution must yield a test case, to remain a permanent part of the project’s test suite*
	- Por otro lado, persiguen detectar nuevos errores considerando que los desarrolladores suelen fijarse más en las partes que ya han fallado pensando en que el código volverá a ser probado con los mismos test, y descuidar otras partes. 
	- Las pruebas retroactivas persiguen probar otras partes del software una vez corregida la parte que fallaba, para detectar posibles errores colaterales en los cambios realizados
- **Las pruebas dependen del contexto de la aplicación**. 
	- Hay que tener en cuenta los riesgos del software que se desarrolle y las distintas necesidades, como las de garantizar la seguridad o la confidencialidad, el cumplimiento con los tiempos de respuesta en sistemas de tiempo real, etc.
- **La falacia de la ausencia de errores**. 
	- Que no se conozcan errores no significa que el software este preparado para su lanzamiento. El caso mas extremo es que no se conozcan errores por que no se hayan hecho pruebas.