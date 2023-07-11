- Proceso de desarrollo de un SI
    - Las tareas a realizar para el desarrollo de SI son las mismas que para cualquier otri sistema informático
    - Etamas desarrollo Software↓ ↓ 
        1. Planificación.
        2. Análisis.
        3. Diseño.
        4. Implementación/Despliegue.
        5. Mantenimiento.
- Componentes de un SI
    - Agentes externos:
        - Definición→cualquier elemento externo al sistema que interaccione con el mismo
            - Pueden ser personas u otros sistemas informáticos.
        - La interacción con el sistema consiste en enviar y/o recibir ↓ 
            - Datos
            - Eventos indicativos de acciones a realizar por el SI (envían) o que informan del estado del SI (reviben)
        - La identificación de agentes externos y sus roles de interacción se debe realizar en la fase de Análisis.
    - Datos:
        - Los datos son un elemento centras de un SI, Cuando hablemos de datos debemos tener en cuenta que estamos hablando de:
            1. Aspectos estructurrales de los datos (variables, dominios...)
            2. Restricciones, que nos indican qué configuraciones de datios almacenados son válidas.
        - Ambos aspectos deben recogerse en la fase de Análisis.
        - El analisis conjunto guiado por las fuentes nos permite recoger todos los datos necesarios para el sistema, y ninguno más, de manera sencilla e informal. 
        - En la fase de diseño se utilizan Modelos de datos conceptuales y lógicos adecuados al SI para reflejar estructuras y restricciones.
        - Analisis de flujo de Datos (DFD)
            - para que sirve un DFD→Es útil para describir el sistema desde el punto de vista de la adquisición, almacenamiento, procesamiento y publicación de datos.
            - Permiten la interacción entre el cliente y el equipo de desarrollo, así como realizar labores de diseño del sistema centradas en los flujos de información entre componentes funcionales del sistema, agentes externos y bases de datos.
        - Ciclo de Vida de los datos ↓ 
            1. Adquisición de los datos
                - Fuentes de datos (usuarios, sensores....)
                - Métodos de adquisición (entrada directa de datos, procesos [ETL](../DDSI/T2⇒Desarrollo de Sistemas de Información/Componentes de un SI/Datos_/Adquisición de datos mediante procesos ETL.md) ...)
            2. Uso de datos en el SI
                - flujos de datos, su transformación y almacenado a través del SI, e interacción con el exterior.
            3. Archivado de datos
                - cuándo y cómo eliminar datos del sistema, y el almacenado de estos datos "obsoletos" para futuras necesidades.
            4. Purgado de datos
                - cuándo y cómorealizar el borrado de datos archivados. 
        - Adquisición de datos mediante procesos ETL.
            - Proceso ETL→Proceso usado para adquirir datos mediante integración de datos de distintas fuentes y/o formatos.
                1. **Extract:** de otras BD, de fichero externos (XML, JSON, texto plano), [web crawlers](https://es.wikipedia.org/wiki/Axiomas_de_Peano), screen scrapping...
                2. **Transform:** limpieza de datos incorrectos o vacíos, transformación de codificaciones, ordenar, mezclar, agregar.... 
                3. **Load:** Comprobación de restricciones semánticas, sobreescritura o almacenamiento histórico, ...
            - Es un proceso complejo que suele utilizar software diseñado para ese proposito.
                - [Listado Software ELT Open source](https://dachival.notion.site/ED-45674dd18c044d1a8d0fb35b3e305200) 
        - Transacciones.
            - Definición→Es una operación lógica que cambia el contenido de la BD. Puede corresponder a una sola sentencia SQL o a varias
            - Hay que determinar si el SI requiere [Atomicidad En Las Transacciones](../../../Atomicidad En Las Transacciones.md).  
            - La mayoría de las implementaciones de SQL permiten la definición y manejo de transacciones, ya que el modelo relacional está pensado para garantizar la consistencia e integridad de la BD a través de la atomicidad
        - Otros aspectos importantes:
            - **Seguridad de los datos:** 
                - Es necesario garantizar el acceso restringido a los datos de acuerdo con las reglas de negocio de la organización
            - **Recuperación de datos:** 
                - Es necesario diseñar estrategias de recuperación de datos ante fallos catastróficos, incluyendo copias de seguridad y protocolos de recuperación
            - **Aspectos éticos y legales:**
                - El Sistema debe garantizar estos aspectos en la adquisición y publicación de datos, particularmente en interfaces de usuario.
    - Software
        - Fundamentalmente dos componentes:
            - Software del SGBD
            - Software de procesamiento de la información
        - Los datos (estructura y restricciones) junto con los requisitos funcionales y no funcionales del SI, van a determinar el modelo de datos a utiliZar, restringiendo los SGBD a usar.
        - Es necesario utilizar un mecanismo de conexión entre el software de procesamiento y el sgbd, que debe estar disponible a través del lenguaje de implementación
        - El administrados de la Base de Datos
            - La implementación del SI requiere la participación y comunicación entre el administrador de la BD y el equipo de desarrrollo
            - Competencias del SBD ↓ 
                - Aprobar el diseño conceptual de los datos del sistema o proponer cambios necesarios para su integración en la BD
                - Colaborar en crear las vistas de usuarios con los permisos de acceso apropiados
                - Adaptar el diseño fisico a los requisitos del sistema
                - Colaborar en la implementación de la funcionalidad del SI a nivel de BD
        - Implementación de funcionalidades a nivel de la BD
            - La mayoría de SGBD actuales permiten la inclusión de código como objetos adicionales en la BD. PAra ello proporcionan al menos un lenguaje de programación.
            - Suele se código que se activa al reallizar operaciones sobre datos, y que sirve para realizar operaciones o comprobaciones que garanticen el cumplimiento de restricciones de integridad.
            - **Donde implementar la funcionalidad de un SI?**
                - Si la funcionalidad en inherente a los datos e independiente de la aplicación concreta. puede implementarse en la bd. En otro caso es mejo, en general, implementarla externamente a la BD.
    - Hardware
        - Dependiendo del tamaño y complegidad un SI puede correr
            - En una computadora al uso en en cualquier LAN
            - En un cluster de ordenadores con una compleja LAN o transfiriendo datos a traves de internet.
        - Es uno de los componentes mas faciles de distinguir (es la unica parte fisica)
- Modelos de Arquitectura para SI
    - La arquitectura de un SI es una definición formal de los procesos y reglas del negocio, estructura, infraestructura técnica y tecnologias empleadas en el sistema.
        - Incluye un inventario detallado del hardware, software y tecnologías red disponíbles, así como planes detallados a medio y largo plazo para su actualización y reemplazo.
    - La arquitectura de un SI suele corresponderse con uno de los cuatro modelos de arquitectura que se presentan a continuación.
    - Arquitectura centralizada
        - ![](https://remnote-user-data.s3.amazonaws.com/4iHpCurQ1tG4L4O0LVrpBQGIvkv_I2-GKAXBQD1xAG5xS833TD5qWqBDbtJUkp37-fi_-VoSFkhpYFt16jwHDGIGmFyfC4ApCm8dLFzg00C9qflys89Doh9QtSxkV6bI.png) ↓ 
            - Es una de las arquitecturas más antiguas en los sistemas de información
            - Los datos y las aplicaciones se almacenan en un sistema central.
            - No existen ordenadores que conecten al servidor sino terminales sin capacidad de cómputo que actúán como periféricos del servidor para proveer de comunicación con el usuario
            - En desuso, aunque podemos encontrar sistemas antiguos funcionando con esta arquitectura
    - Arquitectura Cliente Servidor
    - ![](https://remnote-user-data.s3.amazonaws.com/By70DFl7-mGvEC9aIBWKxCQcJgmlqMjBT_hKsh-M--xZSJEBPqJ6pmBevsHtY2-VpQ0w4LG89XZB3aSiVD9A4EmRuM7I_VRohw-YEIs1Y1056RKKEtXswdBQrrSlcbNM.png)↓ ↓ 
        - Tenemos dos tipos de procesos que suelen ejecutarse en distintas computadoras conectadas por una red de comunicación
            - Proceso Cliente→Realiza peticiones de acceso a la base de datos
            - Proceso servidor→Espera la llegada de peticiones y las satisfacen enviándoles los resultados
        - El software del SI se divide entre procesos cliente y procesos servidor, que se reparten las tareas
        - Debe haber un mecanismo de intercambio de mensajes (peticiones, respuestas) entre los elementos de la arquitectura a través de la red
    - Arquitectura por niveles.
    - ![](https://remnote-user-data.s3.amazonaws.com/GRDSvV6KITmvL6tLTl1e9LY060vrmrbuew89jd4hHjvD3cPnZA7Fq2q7cwjMrDBIu-CnT2TcjSilTZIVW3Y1lQ5R28kE_skvDUpBEYwXA3bhC63Wv-b50uOkbfhXvLbb.png)↓ ↓ 
        - Es una extensión de la arquitectura Cliente/Servidor en la que se crea una capa intermedia para la ejecución de la aplicación de gestión de la información
        - Los PCs de la capa de presentación contienen procesos cliente simples cuya labor queda reglada a la de interfaz gráfica para la comunicación con el usuario
        - Los procesos de la capa de aplicaciones actúan como servidores frente a la capa de presentación y como clientes de la capa de datos. puede haber varios PCs en esta capa y en la de datos
        - Los procesos de la capa de datos actúan como servidores de de datos, conteniendo exxclusivamente el código asociado fuertemente a los datos y común a todas las aplicaciones.
    - Arquitectura orientada a Servicios
        - Es una forma de diseñar e implantar arquitecturas por niveles basada en acoplamiento devil (loose coupling), permitiendo una mejor interoperabilidad entre servicios y clientes implementados en diferentes lenguajes y/o plataformas
        - Se utilizan un conjunto de protocolos y estandarés abuiertos en la web para realizar peticiones de servicio e intercambiar datos entre procesos. proporcionan una capa de abstracción sobre el lenguaje de programación, SGBD y plataforma donde se ejecuta cada servicio
        - Las organizaciones OASIS y W3C son los comités responsables de la arquitectura y reglamentación de los servicios web
        - **Servicio Web**→sistema software diseñádo para soportar la interacción máquina a máquina, a traves de una red, de forma interoperable.
        - Subsistemas ↓ 
            - Provider ⇒proveedor de servicios web
            - Requester ⇒ soliicitante del servicio web
            - Registry ⇒ publicador de servicios disponibles en la web
        - ![](https://remnote-user-data.s3.amazonaws.com/k70TjtJvfhaZIiOm9scENByrHN-2SAWtBVKQpG9SvH1Xn7XbYbuIrYg7HKl65mpd1IPbyt7YPVq50T0tngCtmZFVGXZl2RZ04n97xRBAnyDvo7_XFikpAPkDMWt2A2L3.png)
        - Los protocolos utilizados en esta arquitectura utilizan como base XML y se trasmiten sobre HTTP y otros estandarés web ([WSLD](../../../WSLD.md),[SOAP](../../../SOAP.md),[UDDI](../../../UDDI.md))
    - Criterios Para la elección de una arquitectura
        - 
- 
- 
