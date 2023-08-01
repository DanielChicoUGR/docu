- 
- Agentes inteligentes
    - ![](https://remnote-user-data.s3.amazonaws.com/nBeN9LnowNjX0H8MpAkcSThXzZVN8Hax8yvDZoXZS3kUlYMUN8LonuyUZb0HVqaajTwRR7UVw9ErxAo262J_Ht625r95rFEvdjkP_1Zw1P7kjGguVqhYhsRPrKtH3HZI.png) 
    - 
    - Agentes
        - 
        - ![](https://remnote-user-data.s3.amazonaws.com/l-J3UwydwQ01msdve9yg-eX-ep3V2cZ2_7ZF22EsaLMGA4RaTOcKYVVdKQBLQ65ySbNrTwFqtzwrYmk9hpDgC4n5UwRuAFM16psm7R2mam3lzwVzA5GMn7tI4qiYed0M.png) Definición→Sistema que está situado en un medio que tiene unos sensores y efectores mediante los cuales puede captar información del entorno que le permita tomar acciones que modifican ese entorno y vuelve a percibir para saber que acciones ha hecho
        - Agente Inteligente:
            - Definición→Es un sistema de ordenador, situado en algún entorno, que es capaz de realizar acciones de forma **autónoma **y que es **flexible** para lograr los objetivos planteados. 
            - **Situación**↔El agente recibe entradas sensoriales de un entorno en donde esta situado y realiza acciones que cambian dicho entorno
            - **Autonomía **↔El sistema es capaz de actuar sin la intervención directa de los humanos y tiene el control sobre sus propias acciones y estado interno.
            - **Flexible ** ↓ 
                1. Reactivo
                    - El agente debe percibir el entorno y responder de una forma temporal a los cambios que ocurren en dicho entorno.
                    - Percibe el entorno y lo modifican en tiempo real.
                2. Pro-Activo
                    - los agentes no deben simplemente actuar en respuesta a su entorno, deben de ser capaces de exhibir comportamientos dirigidos a lograr objetivos que sean oportunos, y tomar la iniciativa cuando sea apropiado.
                    - Es capaz de alcanzar objetivos y se los propone
                3. Social
                    - Los agentes deben ser capaces de interactuar, cuando sea apropiado, con otros agentes artificiales o humanos para completar su propio proceso de resolución del problema y ayudar a otros con sus actividades.
                    - No es una característica indispensable.
        - Sistemas basados en agentes
            - **Características que lo definen** ↓ 
                - Sistema en el que la abstraccion clave utilizada es precisamente la de agente
                - Sistema diseñado e implementado con varios agentes interactuando. 
            - Son útiles para:
                1. Problemas con multiples formas de resolverlos
                2. Problemas con multiples perspectivas desde las que afrontarlo
                3. Problemas que requieran multiples entidades para resolverlos.
            - **Interacción entre agentes:**
                - **Cooperación ⇒ **Trabajar juntos para resolver algo
                - ** Coordinación ⇒ **Organizar actividades para evitar las interacciones perjudiciales y explotar las beneficiosas
                - ** Negociación ⇒ **Llegar a un acuerdo que sea aceptable para todas las partes implicadas
    - Sistemas Multiagente 
        - Inteligencia artificial Distribuida:
            - Sistema Multiagente (SMA)→Red mas o menos unida de resolutores de problemas que trabajan conjuntamente para resolver problemas que están más allá de la capacidad individual de cada resolutor del problema
                - Resolutor ⇒ Agente (autonomo y de naturaleza hetereogenea)
        - Características de un SMA ↓ 
            - Cada agente tiene información incompleta, o no todas las capacidades para resolver el problema. asique cada agente tiene un punto de vista limitado.
            - No hay un sistema de control centralizado
            - Los datos no estan centralizados
            - La computación es asincrona
        - Cooperación ⇒ Herramienta fundamental en la formación de equipos
        - Negociacón ⇒ Coordinación y resolución de conflictos.
- Arquitectura de Agentes
    - Arquitecturas deliverativas
        - Sistema de símbolos físicos→Es un tipo de estructyura que trabaja con símbolos y los combina
        - La hipótesis de sistema de símbolos físicos→Dice que tales sistemas son capaces de generar acciones inteligentes.
        - Características ↓ 
            - Habita un mundo que conoce
            - Tiene un esquema interno que representa el mundo
            - Resuelve problemas a través de la manipulación de ese mundo
            - Arquitectura de 3 Capas ↓ 
                - Etapa 1 ⇒ Percibe el mundo y lo refleja en el esquema interno del agente
                - Etapa 2 ⇒ Resuelve el problema de manera computacional y devuelve uyna serie de acciones
                - Etapa 3 ⇒Ejecuta las acciones del plan. 
        - Problemas ↓ 
            - Trasladar en un tiempo razonable lo percibido al esquema interno del agente de manera que sea una representación precisa y adecuada
            - Representar simbólicamente la información del mundo real, y cómo conseguir que los agentes razonen con esta información para que los resultados sean útiles
    - Arquitecturas reactivas
        - Surgen como variación de las arquitecturas deliverativas en la que se suprime la etapa de deliveración del plan. pasando de la percepción a la ejecución de alguna acción
        - Una arquitectura reactivva es aquella que no incluye ninguna clase de modelo centralizado de representación simbólica del mundo, y no hace uso de razonamiento complejo.
- Agentes Reactivos
    - Características ↓ 
        - Se diseñan completamente y por tanto es necesario anticipar todas las posibles reacciones para todas las situaciones
        - Realizan pocos cálculos
        - Almacenan todo lo necesario en memoria
    - Representación del mundo ↓ 
        - Modélos basados en características
        - Modélos icónicos
    - Percepción y acción ↓ 
        - El agente reactivo percibe su entorno a través de sensores
        - Procesa la información percibida y hace una representación interna de la misma
        - Escoge una acción entre las posibles, considerando la información percibida
        1. Transforma la acción en señales para los actuadores y la realiza
        - **EJEMPLO**
            - Supongamos un robot en un mundo dividido en cuadrículas
            - El robot puede percibir si las 8 casillas vfecinas están libres o no, con un senso $S_i$ para cada casilla i
            - El objetivo del agente es llegar a una pared y seguir el borde indefinidamente
            - Tiene 4 posibles movimientos:
                1. Norte
                2. Sur
                3. Este
                4. Oeste
            - No se permite entorno con pasillos estrechos (Anchura<2)
            - ![](https://remnote-user-data.s3.amazonaws.com/uM7IOF5GLzCMPCc7VP_Vpc1yrnvzDxFm6-Eck_feroi1C0r7NdLsnq--HBjvlBhUjFni9utAF_8sqDr3B8nYxqQJt_xnAtpdz_ztsEfA28SmohykBjWt6PPnTdRUbjU6.png) 
    - Arquitecturas de agentes reactivos:
        - Sistemas de Producción:
            - ![](https://remnote-user-data.s3.amazonaws.com/8YJT8apH_0ceRHq82Hwt-ozwodKT_itInIDjGhc8jkM5bADenRU1wl15ehZPtk6dLr-gqnxDiwMIg477um5Y62n21eyI_dZqAxGG1vi_6Dpw5oHuVMquttuV17J-FZam.png)→en donde Ci es una función booleana definida sobre el vector de características, habitualmente una conjunción de literales booleanos.
            - **Ejemplo**
                - ![](https://remnote-user-data.s3.amazonaws.com/rwD6uAF9sAunEZUSoAa3eC5eFAsb3k4lXVqFAqMPiJFZQg41arCK2eAzWguo9bsBPYLcCE8IHemAm5Hd62l9bniGK0dmT1zkTaV75TUTYXG_JQv1nSfQW8rK2zMEGuSp.png) 
        - Redes neuronales:
            - Redes neuronal→Red de unidades lógicas con humbral.
            - ![](https://remnote-user-data.s3.amazonaws.com/nGNI_uhh17gJ8hr4fr8UZX0jYiKbdZ8D9GSbTRJAvHjA4s6Fes_owU3WDspxA9-j4N_Kz-qcvrzSzVtwu2RUatoo8jlwdrDH3ujuqoim98TGsUrhuFCUmto50uV8Hu8F.png) 
        - Arquitecturas de Subsunción:
            - ![](https://remnote-user-data.s3.amazonaws.com/luAe99lXJZewJid3dTpMytgEQE8HI_0EOK--qvI0amOars9dnnV0KsbAsBd7gZHtfzTE0VzDldEWRm6zAvpvMZT-sq_sBXSA1Mi2qRVZKS_hSf72vGndkIJf9HhsK07w.png) 
            - **Características** ↓ 
                - Consiste en agrupar módulos de comportamiento
                - Cada módulo de comportamiento tiene una acción asociada, recibe la percepción directamente y comprueba una condición. Si esta condición se cumple. el módulo devuelve la acción a realizar.
                - Un módulo se puede "[Subsumir](../../../Subsumir.md)" en otro. Si el módulo superior del esquemase cumple. Se ejecuta este en lugar de los módulos inferiores.
        - Arquitecturas reactivas de agentes con memoria:
            - La representación de un estado en el instante t+1 es función de las entradas sensoreiales en el instante t+1, la representacion del estado en el instante anterior t y la acción seleccionada en el instante anterior t.
        - ![](https://remnote-user-data.s3.amazonaws.com/Fgfj1j5DvF4zCId5Aeyw96X9Wf7ksHg3XwPBKYmDQRXzdMXkYvabuqQMFhnaN5sL2V4tBw-R5cFJ1ZrHw7pSIdGULNuR4z6qoQpJ1GnenBoExUnWV9TYVr-aU8lfGQiZ.png) ![](https://remnote-user-data.s3.amazonaws.com/xIsW3-OiNQIBtq6K8_XJsIg1XxD_0KO9oPCYKDfdua-kfvmFcCq3aelOqjqxHWSBoYiXehR1we6I-yjkXTXit8HfbKijnX-zqUJdJ1rqaxlO5uxqTNoiXrySr228QMjA.png) 
        - **Implementación de la memoria con representaciones icónicas **
            - Adicionalmente el agente podría utilizar otras estructuras de datos
                - Ejemplo: Matriz que almacene el mapa con las casillas libres u ocupadas en el momento en el que se percibieron.
            - ![](https://remnote-user-data.s3.amazonaws.com/hi6m8fw_KZC5UXcjOW4AlclYQmQtlayet4bjWra1004wqb8apQ1T_jiCIbjgeyY7LayzyalgcOx7uELrzqTCbzgYK_CmcMo-JNU_vinbDoIHxBENmKqFbfayzr8YpR96.png) 
            - ![](https://remnote-user-data.s3.amazonaws.com/LyHKTL5PcpaMSEqpY8XYxc6xFtmnnzDDpFhZIDFOUwLx210r7OjZM5HF_tafWVYcOBrSDAj3Orlb_kpecvL73e7k7oqFUFt9We9KL9inVcqC4cdFgfVxKVGhWKAZ9yvv.png) 
- 
