- Una arquitectura de 3 niveles
    - Por que organizar en niveles? ↓ 
        - Los datos son accesibles para el usuario desde distintas perspectivas
        - Independencia Lógica↔La organización de los datos puede cambiarse sin afectar a los usuarios 
        - Los usuarios no tienen por que gestionar aspectos relativos a la representación física de los datos.
    - La percepción de los datos en un SGDB puede hacerse siguiendo 3 niveles de abstracción:
        - **Nivel interno **↔** **Constituye la representación de la BD mas cercana a la estructura del almacenamiento físico. por lo tanto, es la capa donde se establece la forma en que se implantan las estructuras de datos que organizan los niveles superiores.
        - **Nivel conceptual **↔** ** Supone una abstracción global de la BD que integra y aglutina todas las percepciones que los usuarios tienen de ella. No debe contener ningún detalle del almacenamiento.
        - **Nivel externo **↔** **A este nivel se definen todas las percepciones particulares de la BD por parte de los usuarios. Cada usuario puede tener su propia visión de la BD.
        - ![](https://remnote-user-data.s3.amazonaws.com/DXWycexOoOcvMvpjjyhHbjn6wRKFkKADs30zkmK4_SwWndwdzRXv3eM5LBEjndsjijls04uURCCbiDVXvEj32nTybeY4ICL6udG4qYm3zgW0hjmZ49v-QRexow_V5i_v.png)  
- Correspondencia entre niveles
    - La transformación o correspondencia entre niveles son un conjunto de normas que definen los datos de un nivel en términos de otro.
    - Transformación conceptual/interna ↓ 
        - Establece como se organizan las entidades lógicas del nivel conceptual en términos de registros y campos almacenados a nivel interno.
        - Tiene independencia física. 
    - Transformación externa conceptual ↓ 
        - Describe el esquema externo dependiendo del esquema conceptual subyacente.
        - Tiene independencia lógica
    - Transformación externa externa ↓ 
        - Característica de algunos SGDB 
        - Permite generar un exquema externo a partir de otro esquema externo
        - Tiene independencia lógica
    - ![](https://remnote-user-data.s3.amazonaws.com/89vp22Ld9tZtnAHCsjJYFw5vLdwfDoP0M4bLk9R5qqRZp6Pr7YgBO5mZdCwY5EfNFGh5HaYM8fO4tx97eBDMomFVGeR1THj2aVHKZh_Moe_y6YQLs0XuMe7QqQ49Dsk2.png) 
- Lenguajes de una BD
    - Se recomienda disponer de un [DSL](../../../../DSL.md) implementado en el propio SGDB 
    - [DSL](../../../../DSL.md) 
        - En la actualidad se presentan bajo una sola implementación con el objetivo de favorecer la adopción de estándares adaptables a varios fabricantes de SGDB
        - Clasificación subpartes:
        - Se compone de 3 sublenguajes.
        - DDL→Data Definition Language
            - Definición→Sublenguaje de definición de datos. Subconjunto del [DSL](../../../../DSL.md) destinado a la definición de de estructuras de datos y esquemas de la BD
        - DML→Data Manipulation Language 
            - Definición→Sublenguaje de manipulación de datos. Subconjunto del [DSL](../../../../DSL.md) mediante el que podemos:
                1. introducir datos en los esquemas, 
                2. modificarlos, 
                3. eliminarlos  
                4. consultarlos. 
                5. Permitir la consulta de la estructura de los esquemas definidos en la BD
        - DCL→Data Control Language 
            - Definición→Sublenguaje de control de datos. Permite gestionar los requisitos de acceso a los datos y otras tareas administrativas de la BD
    - Lenguaje anfitrión/aplicación
        - Definición→Son lenguajes de programación para aplicaciones en el SO que trabajen sobre la BD
        - Estos lenguajes deben disponer de herramientas para trasladar la estructura de datos proporcionada por el [DSL](../../../../DSL.md) 
        - Acoplamiento→Cantidad de operaciones de/sobre una base de datos que tiene implementado un lenguaje anfitrión. 
        - Clasificación según el acoplamiento:
            - Fuertemente acoplados ↓ 
                - Constituidos por lenguajes y herramientas de propósito especifico
                - Se parte del DSL como elemento central del lenguaje en el que incluyen todas las características necesarias para el desarrollo de apps de gestión de BDs.
                - Seria una extensión del [DSL](../../../../DSL.md) dotándolo de características extras. 
            - Débilmente acoplados ↓ 
                - Constituido por lenguajes de propósito general
                - El programador distingue entre las sentencias nativas del lenguaje y las que se usan para acceder a la BD a través del [DSL](../../../../DSL.md). 
                - Se dota al lenguaje de mecanismos para interactuar con el [DSL](../../../../DSL.md) 
            - Métodos de implementar acoplamiento Débil. ↓ 
                - APIs de acceso a la BD
                - Mezclar [DSL](../../../../DSL.md) y Lenguaje anfitrión.
                    1. El programador escribe un código híbrido mezclando [DSL](../../../../DSL.md) y lenguaje anfitrión
                    2. Se preprocesa el código, transformando las sentencias del [DSL](../../../../DSL.md) en llamadas a una API
                    3. Se compila y enlaza con la biblioteca de acceso a la BD
    - 
- Enfoques de una arquitectura de un SGDB
    - Arquitectura Centralizada:
        - ![](https://remnote-user-data.s3.amazonaws.com/WEJxsx8iQ83DBC677W394Rh3IGMCtqym20WdkjV0djynD-e43uJo-e-3nq4CG22Dr8PSOTPkmAm_y37K19yeC00elvfdXs5OjXG4YYjcZVljhExjLzmy4UCanhN5bXxO.png) 
        - Existe un servidor central que absorbe toda la carga de gestión y procesamiento de la información
        - El usuario accede a través de terminales
        - El servidor se encarga de gestionar la BD y las aplicaciones de usuario.
    - Arquitectura Distribuida:
        - De dos etapas:
            - ![](https://remnote-user-data.s3.amazonaws.com/6_tt-rAkS8vffRZuLlzr0-LlLNzSV5zm0zHxos2p4nRSln9J4p2yPvm_5pBQDevCM-Gi8TSibWuwBA46WICOJNAlymK6Bo_S8SgjbGkGMoTt5dpkytfgHex3UHnuEawn.png) 
            - Existe un servidor que escucha las peticiones realizadas en los distintos PCs a través de las aplicaciones de usuario
            - El usuario accede a través de aplicaciones de usuario
            - Los PCs se encargan de todo el procesamiento de los datos (Problema ⇒ Alto coste de mantenimiento)
        - De tres etapas: 
            - ![](https://remnote-user-data.s3.amazonaws.com/jt-ZN9IAGG29nIvlJ83vOyBcmbo-G90OMKW7i9VHMJmcuRKTJnYBBaoWUJH9zFZNuWAllmxlfLhDxDycameqUJldQmLqxVS7MN2vK-qbHw0Z5_KTSwH3m6hs5jXm7qja.png) 
            - **Nivel de Servidor de Datos**:
                - Se puede organizar en un solo servidor central o en una serie de nodos distribuidos 
            - **Nivel de Servidor de aplicaciones:**
                - Se ejecuta la logica interna de las aplicaciones de usuario y son los encargados de procesar y gestionar la informacion que se intercambia con la BD
            - **Nivel de cliente**:
                - Se ejecuta en PCs ligeros manteniendo los estándares propios de la industria con el objetivo de que las aplicaciones de usuario sean lo mas portables posible. 
- El administrador de la BD 
    - Objetivos ↓ 
        1. Elaborar el esquema conceptual de la BD.
        2. Decidir la estructura de almacenamiento en el nivel interno (por defecto registro en archivo de texto).
        3. Realizar el diseño del nivel externo adaptándose a los requerimientos de los usuarios finales.
        4. Definición de todas las reglas de integridad de la BD. 
        5. Definir e implementar una política de privilegios para el acceso a los datos.
        6. Definir e implementar una política sobre recuperación frente a fallos.
        7. Optimizar el rendimiento liberando espacio no usado.
        8. Monitorizar el SGDB para que este operativo el mayor tiempo posible con una eficiencia en cuanto al manejo de los datos lo mejor posible.
- 
--------------------- Portal ---------------------
    - 
- 
- 
