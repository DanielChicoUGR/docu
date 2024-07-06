Es un patron de alto nivel que se utiliza para **describir la organización estructural** de sistemas de Software. Son conceptos **mas abstractos que los patrones de diseño**, que suelen aplicarse a problemas mas concretos y localizados dentro de un sistema.

Define:
- Tipos de componentes y conectores
- Conjunto de restricciones sobre la forma en la que pueden combinarse estos elementos
# Flujo de datos. Tubería y filtro
- **Componentes**
	- **Filtro**. recibe un flujo de datos de entrada y los va procesando de forma incremental, realizando con ellos una transformación y empezando a poner los datos ya transformados en la salida aun cuando todavía no haya consumido todos los datos de entrada que le llegan
	- **Tubería**. Transportan la corriente de datos
# Llamada y retorno
## Abstracción de datos y organización OO
Se refiere a patrones donde el control se pasa de una entidad a otra a través de llamadas y retornos como en la programación estructurada
## Basado en eventos
Facilita la producción, detección, consumo y reacción ante eventos
- **Desacoplamiento**. Los componentes se comunican con eventos, lo que permite una separación clara entre quien emite y quien recibe, mejorando la modularidad y mantenibilidad del código
- **Escalabilidad**. A medida de que el sistema crece, se pueden agregar mas oyentes de eventos sin alterar la lógica central de procesamiento de eventos, lo que simplifica la expansion del sistema
- **Composición sobre Herencia**. Los manejadores de eventos pueden ser compuestos y reutilizados con facilidad, proporcionando flexibilidad en el manejo de diferentes comportamientos
El patron [[Observer]] se adapta a este estilo, donde multiples objetos observan y reaccionan a los cambios en el estado de un sujeto. Es ampliamente utilizado en la programación de interfaces graficas, aplicaciones web y otros sistemas que dependen de la interacción con el usuario o con otros sistemas
## Modelo-Vista-Controlador
- **Modelo**. Lógica de la aplicación. Funcionalidad y estado.
- **Vista**. Representación del modelo. Pueden existir distintas vistas.
- **Controlador**. Interprete de las ordenes del usuario. Manipula el modelo a partir de solicitudes de la vista y actualiza la vista según el modelo, manteniendo la coherencia entre ambos.
## Por capas
Divide la funcionalidad en capas. Cada capa tiene un rol especifico y solo se comunica con la capa superior e inferior a esta.
# Repositorios
Estructura de datos centralizada
- **Centralización de datos**. Los datos son almacenados, gestionados y accesibles por varios subsistemas, facilitando la consistencia e integridad de los datos
- **Desacoplamiento**. Los subsistemas que acceden al repositorio están desacoplados de como los datos son almacenados y gestionados, permitiendo cambios en el almacenamiento sin afectar a los consumidores de los datos
- **Gestion de acceso concurrente**. Asegura que las modificaciones hechas por un subsistema no interfieran incorrectamente con las operaciones de otros
- **Escalabilidad**. Debido a estar centralizado, facilita la escalabilidad y la optimización de almacenamiento y acceso.
# Transición de estados
- **Estados**. Condiciones especificas del sistema. Cada estado define un comportamiento en particular
- **Transiciones**. Cambios entre estados desencadenados por eventos específicos
- **Eventos**. Sucesos externos o internos que provocan transiciones entre estados
- **Acciones**. Operaciones ejecutadas en respuesta a eventos que pueden ocurrir al entrar o salir de un estado durante una transición

Este estilo lo aplican sistemas de control, interfaces de usuario, protocolos de comunicación, juegos, etc.
Da ventaja de claridad en el modelado de comportamiento, manejo simplificado de la complejidad y facilita la reutilización y mantenibilidad del código, pero si no se gestiona adecuadamente, puede introducir un punto único de fallo (el sistema puede fallar)
# Cliente/Servidor
Divide las funciones del sistema en dos partes:
- **Clientes**. Inician solicitudes de servicio, consumen los recursos ofrecidos por los servidores
- **Servidores**. Proveen servicios, procesan solicitudes y gestionan recursos compartidos.
Suelen comunicarse mediante una red, usando protocolos estandarizados
- **Ventajas**
	- Centralizacion de la gestion de recursos y datos
	- Escalabilidad y mantenibilidad
	- Especialización de servidores para tareas especificas
- **Desventajas**
	- Punto único de fallo en los servidores (si falla el servidor, falla el sistema)
	- Escalabilidad de la capacidad de los servidores (pueden saturarse)
# P2P (Peer-to-Peer)
Distribuye las funciones y recursos a través de nodos equivalentes (**Peers**) que funcionan tanto de clientes como de servidores
- **Descentralización**. No hay una jerarquía fija ni un punto central de control, lo que distribuye la carga y reduce los cuellos de botella
- **Redundancia**. La replicación de recursos mejora la disponibilidad y fiabilidad

- **Ventajas**
	- Resistencia a fallos y censura
	- Escalabilidad, cada nuevo peer aumenta la capacidad de la red
	- Eficiencia en la distribución de recursos grandes
# REST (Representational State Transfer)
Se enfoca en la comunicación entre clientes y servidores mediante el concepto de **recursos**, identificados por URIs *Uniform Resource Identifiers*
**Tanto los servicios como los proveedores de servicios son considerados recursos accesibles**
Se utiliza muchísimo en sistemas web
## Principios clave
- **Arquitectura cliente-servidor**
- **Sin estado**. Cada solicitud del cliente debe contener toda la información necesaria para ser procesada. *El servidor no guarda ningún estado de sesión del cliente*
- **Cacheable**. Las respuestas deben poder ser almacenadas en cache para mejorar la *eficiencia y velocidad de las interacciones*
- **Interfaz Uniforme**. Utiliza un conjunto estandarizado de operaciones y formatos de datos para interactuar con los recursos (GET, POST, PUT y DELETE de HTTP)
- **Sistema por Capas**. Puede incluir varias capas intermedias sin afectar a la solicitud o respuesta (balanceadores de carga, proxies de seguridad)
## Formatos de datos y convenciones
- JSON y XML
- Es popular utilizar HTTP, pero no obligatorio
- Se recomienda seguir los principios para fortalecer la relacion entre REST, CRUD y HTTP
# Combinación de estilos