- Herramientas, estilos y estructuras en programación paralela.
    - Trabajos a realizar por el programador/Herramienta. ↓ 
        - **Localización/Detección:**
            - Descomponer la aplicacion en distintas [Tareas](../../../../Tareas.md) 
            - 
            - 
        - **Asignación de **[Tareas](../../../../Tareas.md):
            - Asignar las distintas tareas a distintos flujos de ejecución
        - **Creación/Destrucción de flujos de instrucciones**
        - **Comunicación/Sincronización:**
        - **Asignación de los flujos de instrucciones a Unidades de procesamiento.**
            - Problemas:
                1. Usar mas flujos de instrucciones que unidades de procesamiento
                2. Que los flujos de ejecución cambie de unidad de procesamiento en T.ejec
            - Asignación:
                - Estática:
                    - El reparto de [Tareas](../../../../Tareas.md) entre unidades de procesamiento es el mismo en todas las ejecuciones.
                - Dinámica:
                    - El reparto de [Tareas](../../../../Tareas.md) es distinto en cada ejecución de la aplicación. Solo se conoce el reparto final de instrucciones tras el final de la ejecución de la aplicación. 
    - Herramientas de programación paralela.
        1. Compiladores paralelos→Generan código paralelo a partir de código secuencial.
        2. Lenguajes paralelos→Tienen construcciones particulares del lenguaje asi como compiladores y bibliotecas exclusivas
        3. APIs Funciones→Biblioteca de funciones que se añaden a un a un compilador de lenguaje secuencial.
        4. APIs Directivas→Conjunto de directivas + funciones de una biblioteca que se añaden a un compilador de un lenguaje secuencial.
        5. Lenguajes paralelos para arquitecturas de propósito especifico.→Permiten una mayor configuración de todas las etapas de creación de código paralelo. Consiste en funciones y construcciones del lenguaje así como un compilador exclusivo.
    - Estilos/Paradigmas de programación paralela. 
        - Paso de mensajes:→Los flujos de instrucciones no comparten memoria. Las herramientas deben ofrecer mecanismos para copiar datos de un espacio de direcciones a otro.
        - Variables compartidas:→Los flujos de introducciones comparten memoria, la comunicación se realiza normalmente con variables. La herramienta debe proveer mecanismos para sincronizar el acceso a estas variables compartidas
        - Paralelismo de Datos→Todos los flujos de instrucciones deben ejecutar la misma instrucción sobre distintos datos.
    - Tipos de comunicación entre [Tareas](../../../../Tareas.md) 
        - 
        - ![](https://remnote-user-data.s3.amazonaws.com/_q3zdRT4JhAyy6Pz5ZJkr7T8WpRB5e7DeAOQUdt34gffTobFgZO__AT87LANaUdgqm38mvgHsgcm6JL42nEgLisgOGl0GdbsNbcDKq2NPzihNGHyGwOBZjaxYrbYjg1y.png) 
            - Comunicación uno a todos
                - **Difusión**→Uno de los procesos genera un resultado que tiene que aparecer reflejado en el propio proceso y en todos los demás.
                - **Dispersión **→** **Uno de los procesos envía un dato distinto a cada uno de los restantes procesadores.
            - Comunicación todos a uno 
                - **Reducción **→** **Todos los procesos  envían un dato a uno de los procesadores y estos se combinan con arreglo a una función.
                - **Acumulación **→** **Como el anterior, pero no se realiza una composición, sino que se guarda una copia del dato enviado.
        1. **Uno a Uno**
            - Un flujo de control envía y todos reciben
            - ![](https://remnote-user-data.s3.amazonaws.com/uwGzHf7-XcNNUnv8x_LkxsDeZ9lzjuwU81EclG6rmAvZrzVGJ8KB1g2NLwJlwVC79Rr6Sp2kgdL6X4GH4z0KP6r1h4U0tHB7Zw1AuOgD8o8o4ZVG3WSEfgk6qHiF8Vi-.png) 
        2. **Todos a Uno**
            - Todos los flujos de control envían y uno recibe
            - ![](https://remnote-user-data.s3.amazonaws.com/3kaj5yD2P51ptN4BgXxklZo79BdzLXy-0p5Dwxrvo13xN2AUHi6jFTxqTPL6drIlyiDMvq8sKPZhXIOWusxjJjQkiWll2-R7zIcTEGsa-SB9ffl3LwbrEFgNZrJlByhC.png) 
        3. **Todos a Todos**
            - Todos los flujos envían a todos y todos reciben
            - ![](https://remnote-user-data.s3.amazonaws.com/bjySlUywIt9dG0CwGQ8u8Ng6TzRNnLinMxo4X2lQMh-qhGvVL6z2sw0o93IEHsemK-ppU4RycH9MBKGG5_iJK5itjP4QF32xE3jBCb0EtL5DuM9OlTh-_vtzMm6hZbi4.png) 
        4. **Multiple Uno a Uno**
            - Permutación/desplazamiento o rotación de los datos entre las [Tareas](../../../../Tareas.md) 
            - ![](https://remnote-user-data.s3.amazonaws.com/R0PY4WgEpCC2g22DFCgXeaO5xQf9C4Jb3xh4XllH-lTiKvoE5Ats6F0jgeEcqGRJ7GQlVaLfrRl0C8_dG3z2TKwAyRQkQESuBw0KKvLATXuFNOKdaMTqNZLMhyrf3qmf.png) 
        5. **Comunicaciones Compuestas**.
            - Son combinaciones de estas 3 situaciones:
                1. All reduction ⇒ Todos combinan
                2. Scan ⇒ Recorrido
                3. Barrier ⇒ Barrera
            - ![](https://remnote-user-data.s3.amazonaws.com/X1YU0MwNY8mZKCaOpYmvQTbGNgWVZg40mZLCe7X8e_eS7zy8UVCejT0DTTD3hTOSRMP_iCQm8tBzwPIIGceIHzObuRdMZ98xcbEZ6ono5C1lNecI6nlZ-7o707rBnyEe.png) 
    - Estructuras típicas de códigos paralelos
        1. Maestro_Esclavo ↓ 
            - Hay una hebra máster que se encarga de distribuir el trabajo con el resto.
            - ![](https://remnote-user-data.s3.amazonaws.com/pSktbbldhQAo2qO45Hb89F20SYpgIGX3v9X6MYz0QmjYgcpTkVVeUf-eaIp_JEd1Een-F-MsEClc5z6A7PKadcyBGRbT0kYKqmY4P-T1Qdq-uoB1jDH8T1L-QpLl-9i3.png) 
        2. Cliente_Servidor ↓ 
            - Hay una hebra servidor que recibe las peticiones de las hebras clientes, el servicio devuelve el resultado indicado a la hebra que lo pidió.
            - ![](https://remnote-user-data.s3.amazonaws.com/HMyOO1Y7iR6FOv3aKBBsJv-cDT8VYSMAB_XunzVWQykTxHnP8mWPtZzH-ZFMA_66oGfwktWE7knebZPeaQfJ1VB4Tk7wQWXRf9KZZhfuTKJgZKd56JOmA6QB_NtDKC8_.png) 
        3. Descomposición de dominio ↓ 
            - En este caso tenemos distintas hebras que trabajan con distintos datos. Se asigna a cada nodo un flujo de datos especifico para realizar la tarea asignada. Los distintos nodos se pueden comunicar entre ellos. 
            - ![](https://remnote-user-data.s3.amazonaws.com/Asw8EGM_MWB0YcaryRSAn1t6YQ3QCN5giiYZVRCl299xtasYyPrP77QybTZGKzD8lAqEBjxf-TqPjsrMr-ty6mTQSNpfiiSZAaTrxM-vjPXfvPUNui8b87z-WeHLrPY7.png) ![](https://remnote-user-data.s3.amazonaws.com/cYH85h06nCS9IrjFCFjTjkQJ8_vXqsURx-Fd35z_FNo-duwI5LQDvhCnNTx7ul5HgSBlUtAPbkB_d7LEwJIJfGR_0tIdPJKhyLvJtPZ8QGJe1uXaH5pm5LqB6U8E0JbC.png) 
        4. Estructura Segmentada ↓ 
            - Tenemos un numero de procesos que ejecutan tareas distintas sobre datos distintos.
            - Se llama segmentada porque los datos suelen ir pasando P(n-1) a P(n)
            - ![](https://remnote-user-data.s3.amazonaws.com/wk45Za_Lnd9mO1WJXU4fABlgA6qT6f46whVKXU182cSeAXwo4VpjLH7VJAMHYamXv7tLhc4eDJex5Z-NLhr9IxZ9pUw219x3KzlwFkqdz_o4DG5Rz_kXhWcbu5hDqIdb.png) 
        5. DyV/Descomposicion Recursiva ↓ 
            - Consiste en descomponer una tarea en distintas subtareas, resolverlas y juntar los resultados para obtener el resultado final.
            - ![](https://remnote-user-data.s3.amazonaws.com/MVtk57B7TfWHylrQ234xIf21tBesUTPQkiDmbkyac86EvnFDDYQ1hT1nTR6mRnOCI98BTafbChYsGmQbmwBQHwM3Ew1kpDXWIiU84nwCAl0I4J-xUqqMuCfg9_4dy8Iw.png) 
- Proceso de paralelización.
    - Tareas:
        1. Descomponer en tareas independientes:
            - Para la descomposición hay que analizar la dependencia entre las distintas funciones así como las iteraciones de los bucles.
        2. Asignar (Scheduling+mapping)
            - Scheduling→Agrupar tareas y procesos
            - Mapping→Distribuir la ejecución de las distintas tareas y procesos en las distintas unidades de procesamiento.
            - Elementos a tener en cuenta: estática 
                1. Numero de Cores ⇒ Improducente crear mas hebras que numero de cores
                2. Coste de comunicacion y sincronizacion (overload)
                3. Equilibrio de carga ⇒ en el momento de la sincronizacion, las hebras han de acabar en tiempos similares las taeras.
                    - El equilibrio depende de:  ↓ 
                        - La arquitectura ⇒ Los nodos comparten velocidad o no (importante arquitectura big-little)
                        - La descomposicion de las tareas en las distintas hebras y processos.
            - Tipos de asignación de Tareas:
                - **Estática**↔Es aquella en la que la tarea que se asigna a cada hebra ya aparece indicado por el propio código (ya sea escrito por el programador o insertado por al herramienta)
                - **Dinámica**↔Se realiza en tiempo de ejecucion , de manera que la asiganción se va haciendo durante la ejecución. Esto lo puede indicar el programador o la herramienta.
        3. Redactar
            - Escoger la herramienta de programación paralela que ayude a solucionar el problema de la manera mas eficiente
        4. Evaluar 
            - 
- 
- 
