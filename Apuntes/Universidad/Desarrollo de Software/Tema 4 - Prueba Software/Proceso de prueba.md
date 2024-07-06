[[Modelos del proceso de prueba]]
![[Drawing 2024-06-18 20.01.07.excalidraw.svg]]
## Planificación y control
- Decidir a grandes rasgos que se quiere probar y como, quien lo hara y cuando, y que criterios se usaran para decidir cuando terminan las pruebas
- El control incluye todas las actividades de seguimiento de la planificación y de reajuste entre el plan y la realidad
## Análisis y diseño
### Análisis
- Revisar las especificaciones de requisitos, arquitectura, diseño, interfaces y otras partes que deben ser la base para elegir las pruebas
- Elegir los elementos a probar y analizar su especificación para identificar las condiciones y datos requeridos para probarlos
### Diseño
Especificar como combinar estas condiciones de tal forma que impliquen pocos casos de prueba, que datos se usaran para hacer las pruebas y cuales son los resultados que un código correcto debe dar en unas condiciones concretas. Se dice que el caso de prueba pasa si el comportamiento esperado es exactamente igual al obtenido. De forma mas especifica, estas son las tareas que se contemplan en el diseño
- **Casos de prueba**. A partir de los elementos elegidos para probar y sus condiciones, especificar los casos de prueba a realizar, incluyendo su priorización
- **Entornos de prueba**. Detallar como debe ser cada entorno de prueba y si se requiere alguna infraestructura y herramientas especificas para las pruebas
- **Datos de prueba**. Especificar los datos de prueba concretos que serán evaluados
## Implementación y ejecución
- Codificar los procedimientos o métodos para los distintos casos de prueba, crear datos para la prueba y preparar los marcos de prueba automatizados y [[Arnés de prueba|arneses de prueba]] que se necesiten
- Ejecutar los casos de prueba en un orden determinado, de forma manual o mediante herramientas de ejecución automática de colecciones de pruebas que ejecutaran los tests en serie para ganar en eficiencia
- Mantener un registro de las actividades probadas incluyendo:
	- La version del software, los datos, herramientas y el [[Testware]] usado
	- Los resultados, comparándolos con los esperados, incluyendo cuando no se cumple lo esperado, si es posible, un análisis de causas
	- Informar de las diferencias, si las ha habido, distribuyendo este registro
	- Donde sea necesario, repetir las actividades de prueba cada vez que se cambia el código para corregir los fallos detectados por las pruebas. Esto incluye volver a ejecutar el mismo test, ejecución de un nuevo test que sea correcto y pruebas de regresión
## Evaluación y reconsideración de los criterios de salida e informe
En esta fase debemos decidir cuando parar de probar y comunicar los resultados a las partes interesadas. Se contemplan así las siguientes actividades.
- Comprobar si se ha alcanzado el criterio de parada que se había fijado
- Determinar si se necesita seguir probando o si el criterio fijado debería ser modificado. A veces podemos incluso alcanzar un objetivo fijado (por ejemplo, una cobertura del 85%, pero surge la necesidad de mas pruebas)
- Comunicar a las partes interesadas los resultados finales de las pruebas
## Actividades de cierre
Una vez que se haya decidido terminar con las pruebas, se debe dar termino a un proceso de pruebas con las siguientes actividades de cierre:
- Asegurar que la documentación este en orden y que el producto a entregar este finalizado, cerrar los incidentes y actualizar los cambios en futuras entregas, documentando que el sistema ha sido aceptado
- Cerrar y archivar el entorno, infraestructura y el [[Testware]] usados
- Pasar el [[Testware]] al equipo de mantenimiento
- Redactar las lecciones aprendidas con el proyecto de prueba para mejorar los futuros procesos de prueba