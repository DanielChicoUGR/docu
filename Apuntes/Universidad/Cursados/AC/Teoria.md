- Tema 1⇒Arquitecturas paralelas: Clasificación y prestaciones.
    - Clasificación del Paralelismo implícito en una aplicación
        - Tipos de paralelismo
            - [Paralelismo Implícito](../../../Paralelismo Implícito.md) 
                - Criterios de clasificación del [Paralelismo Implícito](../../../Paralelismo Implícito.md) 
                    - Granularidad
                        - Definición→Tamaño de lo que se puede ejecutar en paralelo
                        - < Tamaño ⇒ Granularidad mas fina
                        - ![](https://remnote-user-data.s3.amazonaws.com/1QRqMSKiR9oIiR0Qz41XRM56BiKxcnP6sVBQ8pDwEUxi_c6XW4H2upRNhFljQDrzl05x-xrqzTRD_Kud218yNDpyq5459LmJRZq_Kn1ciis_i4oVS6VJK73xd91mvgat.png) 
                    - Paralelismo de Tareas ([TLP](../../../TLP.md)) 
                    - Paralelismo de Datos ([DLP](../../../DLP.md)) 
                    - 
            - [Paralelismo Explicito](../../../Paralelismo Explicito.md) 
                - Criterios de clasificacion del [Paralelismo Explicito](../../../Paralelismo Explicito.md)
                    - **Proceso:**
                        - Contiene:
                            - Codigo programa
                            - Datos de la pila
                            - Contenido de los registros
                            - Tablas de ficheros abiertos
                        - Para comunicar procesos se hace uso de llamadas al SO.
                    - **Hebra:**
                        - Una o mas hebras componen un proceso
                        - Contiene:
                            - Su propia pila
                            - Sus propios valores de los registros del procesador
                        - Para comunicarse entre hebras del mismo proceso se usa memoria compartida, haciendo que la comunicación sea mas rápida.
                    - **Instrucción:**
                        - La unidad de control de un core o procesador gestiona la ejecución de instrucciones. 
            - Detección y extracción del paralelismo:
                - ![](https://remnote-user-data.s3.amazonaws.com/UFABImXWMR6p-RotzLnRxRn8EqbyzQK3Jgy01me5MQ4FHkpI5lagitJwYG4oCpJ1WhV8MKuZpfohgODzdZdt78lhJyT1ygH4ij2sImGMcvZ-ToAJo4Qc_Dp38W7yGnG5.png) 
        - Dependencia de datos
            - Definición→Se establece una dependencia entre datos cuando 2 bloques de ejecución hacen referencia a una misma dirección de memoria, de tal forma, que se tendrá que ajustar el cauce de ejecución para que el resultado final no genere incongruencias.
            - Tipos de dependencias:
                - RAW (Read after Write)
                    - ```c
int a,b,c,d;

a=b+c;
//Codigo que no usa a
d=a+c
``` 
                        - Peligro?→Al ejecutarlas en paralelo, hay que cerciorarse que la primera instrucción en ejecutarse se "a=b+c". Si no fuera así, el valor de la variable d, no seria el correcto según indica el código secuencial.
                        - 
                - WAR (Write after read)
                    - ```c
int a,b,c,d;

d=a+c;
//Codigo que no usa a
a=b+c;
``` 
                        - Peligro?→Similar al RAW, si se llegase a ejecutar primero la segunda instrucción en secuencial, el valor de d seria incongruente con el valor mostrado en caso de una ejecución secuencial.
                        - 
                - WAW (Write after Write) ⇒ 
                    - ```c
int a,b,c,d,e;

a=b+c;
//se lee a
a=d+e;
//se lee a
```
                        - Peligro?→Sin un control de la paralelizacion, el valor de a podría ser inconsistente dado el momento. Un caso, Se ejecuta a=b+c y acto seguido a=d+e, siempre que a partir de ese momento, ya sea tras la primera o la segunda instrucción. Siempre se leerá el resultado de la segunda
    - Clasificación de Arquitecturas Paralelas 
        - [Computación Paralela](../../../Computación Paralela.md)
        - [Computación Distribuida](../../../Computación Distribuida.md) 
        - Clasificación Comercial
            - Se clasifican en función de su coste y del uso que se les vaya a dar
            - ![](https://remnote-user-data.s3.amazonaws.com/u53lipY9K-wB798wZJrSW66iXT-EsV4rVUEMR5bF1HXpA6V-aOb5t51oCYs2OO__v-1u9KcFQ_50CaCw8KsY_fWb2NXmkaCLExnJ5OiEF6P4DnAW9gYXHoouHqZpENeR.png) ![](https://remnote-user-data.s3.amazonaws.com/L5t0IGyZoQpCK6l0k-zGle7KuBf-FAY1n_jusp1G-lVuU7NFJQ8x7JXeXvEKbbhOr2igBkuP3bTY93BJXUHU1PM3hU269n4qn78syGPoecLuPMAM2zGCSk9UEtheBA6w.png) 
        - Clasificación para educación/investigación/industria. 
            - Clasificación de FLINN (Según el flujo de instrucciones) 
                - ![](https://remnote-user-data.s3.amazonaws.com/nIWYMv2QLGUHP3B8fcmJxPstEbgJFYaRByoVP79FuIoW_WWuuLPH2XDyAWzBYzp0VufnmmarK1PzR38LvK4XJFKNA1rd-cTn_Qefh7Ljb79YFRxqBXhfg-ewTRZZoje8.png) ![](https://remnote-user-data.s3.amazonaws.com/DG1GFOJPeKDWWT1K_86Xtx_FkFZkEhSDJAVcEowzBgqKYNoF62tllMhWIqp8LR0mg0Rp2plekV_2AFDJd80r7kBHg4JroVt-Mb4z8vrw06Lg0VUYygoW9pasPbV3VZ3d.png) 
                - **Arquitectura SISD** ↓ 
                    - Corresponde a los procesadores de un único núcleo
                - **Arquitectura SIMD ** ↓ 
                    - Existe una única unidad de control enlazada con múltiples unidades de procesamiento
                    - Aprovecha el paralelismo de datos. Útil para procesadores matriciales y vectoriales
                    - Uso extendido en GPUs a día de hoy
                - **Arquitectura MISD** ↓ 
                    - Permite Cargar un flujo de instrucciones que afectaran a un mismo flujo de datos
                    - Permite que el output de una instrucción sea el input de la siguiente
                    - No existen computadoras de proposito general con este diseño
                    - Se puede simular por software a través de un MIMD
                - **Arquitectura MIMD**  ↓ 
                    - Existen mas de un flujo de instrucciones para flujos de datos distintos.
                    - Permite aprovechar paralelismo real
                    - Es la arquitectura mas usada a día de hoy para cpus de propósito general.
                - **Clasificación de la Arquitectura MIMD según el sistema de memoria implementado** 
                    - Existen dos grandes grupos:
                        - [Multicomputador](../../../Multicomputador.md)
                        - [Multiprocesador](../../../Multiprocesador.md) 
                    - **Diferencias:**
                        - ![](https://remnote-user-data.s3.amazonaws.com/z0PMrM1bQjWfac1fl5P6pJzh5CrPNd3IstDUypmyan_2SWxRg8zt0R6SvoM3uomfajNsAK3YDFZbIdrQZndpZZvUxx7wS6JIhWmujzftHMHMARCu6eBsdmus8JqMzgZA.png) 
                        - ![](https://remnote-user-data.s3.amazonaws.com/f8W_QxDDF8reOrFQPbiTO-qVQPveN5I6WspduposFQcxU3S4jaVArPDgcCiazYy8wPX8vmPR0twk7uKxyeJgspd5cWifhzuca2ReGgLvmOc7edqofcmD_v9ksNM0JN2m.png) 
                            - NORMA↔Memoria distribuida físicamente, comunicación a través de mensajes.
                            - NUMA↔Memoria físicamente distribuida pero tratada en conjunto como una única memoria. Genera tiempos de acceso a memoria poco consistentes en función de la "cercanía" del dato a buscar.
                            - CC_NUMA↔Como un NUMA pero con protocolos Hw y Sw para la coherencia de caches
                            - COMA↔Cada memoria local actúa como una cache del procesador. La memoria interna del sistema es al suma de todas las caches de los procesadores.
    - 
    - 
- Tema 2 ⇒ Programación paralela
    - Herramientas, estilos y estructuras en programación paralela.
        - Trabajos a realizar por el programador/Herramienta. ↓ 
            - **Localización/Detección:**
                - Descomponer la aplicacion en distintas [Tareas](../../../Tareas.md) 
                - 
                - 
            - **Asignación de **[Tareas](../../../Tareas.md):
                - Asignar las distintas tareas a distintos flujos de ejecución
            - **Creación/Destrucción de flujos de instrucciones**
            - **Comunicación/Sincronización:**
            - **Asignación de los flujos de instrucciones a Unidades de procesamiento.**
                - Problemas:
                    1. Usar mas flujos de instrucciones que unidades de procesamiento
                    2. Que los flujos de ejecución cambie de unidad de procesamiento en T.ejec
                - Asignación:
                    - Estática:
                        - El reparto de [Tareas](../../../Tareas.md) entre unidades de procesamiento es el mismo en todas las ejecuciones.
                    - Dinámica:
                        - El reparto de [Tareas](../../../Tareas.md) es distinto en cada ejecución de la aplicación. Solo se conoce el reparto final de instrucciones tras el final de la ejecución de la aplicación. 
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
        - Tipos de comunicación entre [Tareas](../../../Tareas.md) 
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
                - Permutación/desplazamiento o rotación de los datos entre las [Tareas](../../../Tareas.md) 
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
- Tema 3 ⇒  Arquitecturas con paralelismo a nivel  de hebra ([TLP](../../../TLP.md))
    - Arquitecturas con [TLP](../../../TLP.md)
        - Clasificación y estructuras de arquitecturas con [TLP](../../../TLP.md) explícito y una instancia del SO
            - Estructuras ↓ 
                - Multiprocesador→Ejecuta un flujo de instrucciones distintos en cada uno de los distintos procesadores/cores físicos de los que dispone el sistema.
                - Multicore ( __multinulcleo__ )→Ejecuta distintos flujos de intrucciones dentro de un mismo procesador con varios nucleos fisicos. Una thread para cada nucleo.
                - Núcleo ( __Core) multithread__ →Núcleo al que se le ha modificado su arquitectura [ILP](../../../ILP.md) para ejecutar flujos de instrucciones en paralelo.
        - Multiprocesadores
            - Criterios de clasificación:
                1. **Sistema de memoria**
                    - [NUMA](../../../NUMA/NUMA.md) 
                        - Mayor latencia, poco escalable
                        - 
                    - [UMA](../../../UMA.md) 
                        - Menor latencia, mas escalabilidad pero una mayor dificultad a la hora de escribir el código.
                    - ![](https://remnote-user-data.s3.amazonaws.com/Tn7Fw7g73W2pXTMoXBJUyXS66lac9c8VMPePTehtBtrBolA-iBuWcSz6VsfETAICzEJhm-DSDBvhoaH3pub3ENhNL8a475m446u7rjnF7G7vwbK3Hq_mNYbsefmT-T1d.png) 
                2. **Nivel de empaquetamiento:**
                    - ![](https://remnote-user-data.s3.amazonaws.com/dzCMWMW68UUbIGcIuEiQBpK5xKYe1YvB2p_kvjxoBLdwVWg5CIsznxDWL6VGUWSSeUGcmraMa8I58Cky8rb7s9ZosI7smN0DQKAY2f9d9AV-4yIS2AMf4tj1Nx-ijrpS.png) 
        - Multicores 
            - Ejemplos Estructuras:
                - ![](https://remnote-user-data.s3.amazonaws.com/31SW4nXFqm0KySLhpNAkA1oEJMozbjM2bOpX2BqFAwMfM9Je_SixwirR4tPTiVxTyZXPcMnCVv-MzcsRpITEIYyyvf1HRtCkhoUhEtM02Seg1A3QTWy591en9BEPXex-.png) 
                - ![](https://remnote-user-data.s3.amazonaws.com/eXejJWQoy_du268t4vZcHH5xK2HF-iFr3LN1p3PfP_HLW80KJxIkQ91-eF9Or_LGXIbF3R-BUfDMj88x61zEC4xJ0bX1lqKYquSfwmxTL8NfTEgVRcgA1y2kbrrG80EW.png) 
            - 
    - Coherencia del Sistema de Memoria
        - ![](https://remnote-user-data.s3.amazonaws.com/Mqz1KvbBk66kObngO3H2Lluax8A8XCs1vGKuWb41X8C3-CMdYJOSm6Yo-SKCWhS_rRte7m3sOAgqG-hf8vNdYoheaoaDYjyqweRtwLNH7qLZFmxi9P05NbJNtLnvDxZR.png) 
        1. Sistema de Memoria en multiprocesadores.
            - Que incluye? ↓ 
                - Cache para todos los nodos/cores
                - Memoria Principal
                - Controladores 
                - Buffers
                - Medio de comunicación de todos estos componentes (red de interconexión) 
            - La comunicación de datos entre procesadores la realiza el sistema de memoria
                - La lectura de una dirección de memoria debe devolver lo último que se ha escrito (desde el punto de vista de todos los componentes del sistema)
        2. Concepto de coherencia en el sistema de memoria. Situaciones de incoherencia y requisitos para evitar problemas en estos casos.
            - ![](https://remnote-user-data.s3.amazonaws.com/Vqg-Ns9A63j-4n4qr6mYHEeeRuBst2HbGNBRLGc7M77nsq3JZGzyDd96iHPxQwqYGySq7O1sBznzV8bC_cRXR_Nkw5VGqNHZWnrShi-fzKjZYx9S-YDsaax9PLuP4Fpu.png)
                - Métodos de actualización de memoria principal implementados en cache:
                    - **Escritura Directa (write-through) **→** **Con este mecanismo no se permiten las situaciones de incoherencia entre la cache y la memoria principal ya que esta se actualiza tras cada modificación de una dirección en la cache.
                        - En aplicaciones ejecutadas en un computador, tras modificar una dirección de memoria en cache, se escribe al poco tiempo en memoria siguiendo los principios de  __localidad espacial y temporal. __ Esto genera un acceso continuo a memoria haciendo mas rentable reescribir el bloque completo donde se encuentra la dirección de memoria antes que solo esta. 
                    - **Postescritura (write-back) **→Con este sistema, el bloque se escribe en memoria principal cuando se desaloja de la caché para dar espacio a un nuevo bloque. Evitando escrituras innecesarias en Memoria Principal. En cambio las copias de ese bloque en otras cachés si han de actualizarse a traves de algun protocolo de difusión.
                        - Lo mas usual es dotar al bloque de información de un bit de estado que identifique cuando una dirección ha sido actualizada para pedir la nueva copia a la caché mas actualizada.
            - Mecanismos de prevención de incoherencias entre cachés:
                - Para evitar una situación de incoherencia entre las cachés se deben de cumplir **2 CONDICIONES:**
                    - **C1 Propagación de escritura **→** **Se debe garantizar que todo lo que se escribe en la copia de un bloque en una caché se propaga a las copias del bloque en otras cachés.
                    - **C2 Serialización de escrituras **→** **Se debe garantizar que las escrituras en una dirección se ven en el mismo orden desde todos los procesadores (es decir, el sistema de memoria debe parecer que realiza las operaciones una detrás de otra de manera atómica).
            - Mecanismos de propagación de escrituras a otras cachés:
                - **Escritura con actualización (write-update)**→** **Cada vez que el procesador escribe en una dirección en su caché se escribe también en las copias de esa dirección en otras cachés. Si se cumplen los principio de localidad espacial  o temporal puede generar trafico innecesario.
                - **Escritura con invalidación (write-invalidation) **→** ** __Antes de que un procesador modifique una dirección de memoria se invalidan __ todas las copias del bloque que contiene esa dirección de memoria. Cuando eventualmente un núcleo quiere acceder a un bloque invalidado. Pide una copia a la caché mas actualizada o a memoria. Necesario incluir esta información en la información de estado del bloque.
                - La propagación en las escrituras se puede realizar:
                    - Difusión a todas las caches del paquete que se va a modificar (los multiprocesadores UMA pueden llevar este mecanismo implementado por hardware a través de un bus especifico de copia de datos entre cachés)
                    - Envío selectivo a las caches con la copia del bloque (implica almacenar mas información sobre que caché almacena que bloque de memoria)
        3. Protocolos de mantenimiento de la coherencia: Clasificación y diseño.
            - Protocolos de espionaje (snoopy).
                - Para buses, y en general sistemas con una difusión eficiente
            - Protocolos basados en directorios.
                - Para redes sin difusión o escalables(multietapa y estáticas).
            - Esquemas Jerárquicos.
                - Para redes jerárquicas
            - Protocolos de mantenimiento de coherencia.
                - **Políticas de actualización** ↓ 
                    1. Escritura Directa
                    2. Postescritura
                    3. Mixto 
                - **Políticas de coherencia de caché/comportamiento** ↓ 
                    1. Escritura con invalidación
                    2. Escritura con actualización(inmediata)
                    3. Mixta
                - **Descripción del comportamiento** ↓ 
                    1. Posibles estados de un bloque en caché.
                    2. Posibles estados de un bloque en memoria principal.
                    3. Los paquetes que genera el controlador de la **caché**.
                    4. Los paquetes que genera el controlador de la **memoria principal.**
                    5. Definir las transiciones de estados para los bloques.
        4. Protocolo MSI de espionaje (Modified-Shared-Invalid).
            - Estados bloque en caché ↓ 
                1. **Modificado (M) ⇒** un bloque en este estado es la única copia del bloque de memoria en todo el sistema. El controlador debe responder con el bloque si le llega con el bus una peticion con lectura del bloque o escribirlo en memoria si se reemplaza por otro.
                2. **Compartido (C,S) ⇒** un bloque en este estado en caché es valido, también se encuentran copias de este bloque en otras cachés o en memoria principal. El controlador ha de invalidarlo si lee una petición de invalidación en el bus.
                3. **Invalido (I) ⇒** o bien el bloque se encuentra en la cache pero con información desactualizada o bien ya no se encuentra en caché. Cuando el procesador intenta acceder a este bloque se genera un fallo de caché y el controlador envía la petición pertinente por el bus.
            - Estados de un bloque en memoria ↓ 
                - **Válido ⇒ **el bloque está actualizado en memoria principal y puede haber una copia valida en varias cachés. El controlador responde con el bloque si ve en el bus una petición con lectura de un bloque con este estado.
                - **Inválido** ⇒ el bloque no está actualizado, existe una copia valida en una caché. 
            - Notación paquetes: 
                - Paquetes que genera un controlador de caché ↓ 
                    - PtLect(B) ⇒ petición de lectura del paquete B (se genera tras un fallo de caché del nodo).
                    - PtLectEx(B) ⇒ Petición de acceso exclusivo a un bloque con lectura. (se genera tras una petición de escritura del procesador cuando tiene una copia invalida del bloque en caché).
                    - PtEx(B) ⇒ Petición de acceso exclusivo al bloque B. (Se genera por lo general tras una peticion de escritura sobre un bloque en estado compartido, como respuesta a este comando se invalidarian las copias del resto de cachés
                    - PtPEsc(B) ⇒ Petición de posescritura de un bloque. Reemplazo de un bloque a estado modificado (se actualiza en MP)
                    - RPBloque(B) ⇒ Respuesta con bloque. (Se genera cuando se tiene un bloque en estado modificado y se obtiene una peticion de lectura (exclusiva o no) del exterior. Alberga el bloque de memoria en su interior).
                - Paquetes que genera el controlador de Memoria 
                    - Solo emite paquetes de respuesta ante peticiones de lectura Si y solo SI se almacena en memoria una copia valida del bloque. Siempre responde pasando una copia por el bus. Si un controlador de caché también responde a la petición el controlador que recibe la copia se encargará de discriminar la respuesta de MP.
            - Relación de acciones con eventos recibidos y estados. 
            - ![](https://remnote-user-data.s3.amazonaws.com/Qpi7IsPon_L4T_Bp6lflsRQG_Ojm79KhKU5jiWiQO0E75_SgYrvC3YUu-BcbGmFg7grFt4pk2MZlHGXK6IPHZGyX32T0sXULyEmW8BCUpbmsyUwbXnj1Sh3SpeLvWANs.png) 
        5. Protocolo MESI de espionaje. 
            - Siempre que con el protocolo MSI se escribe en la copia de un bloque en una caché se genera un paquete de petición con acceso exlusivo al bloque con el objetivo de invalidar el resto de copias. Esto genera trafico innecesario si solo existe una copia en la caché. 
            - El protocolo MESI separa el estado compartido en dos:
                - **Exclusivo (E) ⇒ **No hay copias del bloque B en otras cachés
                - **Compartido (S) ⇒ **Existe al menos otras copia del bloque B en otra caché. 
            - Se genera una nueva tabla de relación de acciones:
            - ![](https://remnote-user-data.s3.amazonaws.com/3n2xvunLvtrlOyrs2c_tM9xxn2PUhgYo6eTgC4yPhJ_cLHdv4EKZG146mujuiQTGt80Iz1cJGEOr92p8mUiQ5d1F328cAZjaN9dfAWdDHEj3APYWymHV59BVI7wu0Y8I.png) 
        6. Protocolo MSI basado en directorios con o sin difusión. 
            - Clasificación nodos cómputo:
                1. Nodo solicitante de un bloque (**S**) ⇒ Genera una petición de un bloque.
                2. Nodo origen de un bloque (**O**) ⇒ En un multiprocesador [NUMA](../../../NUMA/NUMA.md)  la memoria está repartida físicamente, haciendo que una sección del espacio de direcciones esté más cerca físicamente que el resto. El nodo  __home __ de un bloque de memoria es aquel e el que se aloja físicamente le bloque. 
                3. Nodo propietario de un bloque (**P**) ⇒ Es un nodo que tiene una copia valida de un bloque en su caché.
            - Protocolo MSI para Multiprocesadores [NUMA](../../../NUMA/NUMA.md) sin difusión:
                - Como no se usa difusión, ha de almacenarse en memoria principal, además del estado del bloque en memoria, información sobre las cachés con copia del bloque para que las invalidaciones se puedan propagar a los nodos con una copia valida del bloque.
                - 
    - Consistencia del Sistema de Memoria
        - Consistencia de memoria→Especifica las restricciones en el orden en el cual las operaciones de memoria deben parecer haberse realizado.
        - Coherencia de memoria→Especifica las restricciones en el orden en el cual las operaciones sobre una dirección de memoria parecen haber sido realizadas.
        - Consistencia Secuencial: 
            - Es el modelo de consistencia que se suele usar en las herramientas de alto nivel.
            - Requiere de ↓ 
                - **Orden del programa**→Las operaciones de memoria que ejecuta cada flujo de instrucciones deben realizarse en el orden descrito por el código que ejecuta el flujo de instrucciones.
                - **Orden Global **o **atomicidad**→**  **Todas las instrucciones de memoria parezcan ser ejecutadas una cada vez ⇒ Serialización global. 
        - Modelos de consistencia relajados:
            - Son aqueyos que relajan el cumplimiento de las condiciones de la CS con el objetivo de incrementar las prestaciones.
    - Sincronización 
        - Soporte Hardware y Software de sincronización.
            - ![](https://remnote-user-data.s3.amazonaws.com/PmjKn5IF6bANc9G2XvPmyBNQ1h-AVQZsUUBWVp1zVUdS02PpPTZyBaqc3hekN9YTnYkkgvEONM7D7lFvMDXbA6-NphhCAaJTi3xSLLgKivazKP2uu2H4E4EZL278nuZJ.png) 
        - Cerrojos:
            - Estructura software que permite la sincronizar varios flujos de instrucciones mediante dos operaciones:
                1. **Lock()** 
                    - Un flujo de instrucciones ejecuta el lock() cuando quiere acceder a una SC (adquiere el cerrojo/lo ciera)
                    - Requisitos a cumplir:
                        1. Si hay varios flujos que intentan la adquisición a la vez solo uno de ellos puede entrar
                        2. Todos los cerrojos que ejecuten lock() con el cerrojo cerrado tienen que esperar.
                2. **Unlock()**  
                    - Todo flujo deve ejecutarlo al terminar de acceder a las variables compartidas para que el resto de las hebras puedan ejecutar su SC.
                    - El objetivo es liverar solo uno de los flujos que estaban esperando.
                        - Requisito ⇒ Si no hay flujos en espera, permitirá que el siguiente flujo ejecute lock() sin esperar.
            - **Implementaciones:**
                - Cerrojo Simple: ↓ 
                    - Implementación mas sencilla de todas, Toma de una variable compartida k que toma dos valores(1 ⇒ cerrado, 0⇒ abierto).
                    - ```cpp
void lock(k){
	k=0;
}

void unlock(k){
	while(leer-asignar_1-escribit(k)==1){}
}
``` Funcion
                    - 
- Tema 4 ⇒  Arquitecturas con Paralelismo a  nivel de Instrucción ([ILP](../../../ILP.md))   
    - La velocidad de un procesador esta relacionada con las instrucciones por ciclo y la frecuencia. $Vcpu=IPC*F$
    - Clasificación de cores Multithread:
        1. **Temporal Multithreading (TMT)**→La conmutación entre threads la decide y controla el hardware. Emiter instrucciones de un unico thread por ciclo.
            - Clasificación cores con TMT
                1. **Fine-grain Multithreading (FGMT) **→La conmutación de hebras la decide el hardware en cada ciclo (coste 0). Procesadores de tipo temporal en la que en cada ciclo puede pasar de una hebra a otra. Funciona por turno rotatorio (Round Robin) o por eventos de cierta latencia.
                2. **Coarse-grain Multithreading (CGMT) **→ 
                - 
        2. **Simultaneous Multithreading (SMT) **→Ejecutan en un cores superescalar varios thread en paralelo. Puede emitir instrucciones de varios thread por ciclo.
    - Microarquitecturas [ILP](../../../ILP.md).Cauces Superescalares
        - ![](https://remnote-user-data.s3.amazonaws.com/sIuU60LhU8ge9igoaQsqNWaAs4wm1If4NIvxBX78Fnp9SzjEF7-s5uIYXByjYmp1NEumeISCeFPDguotlPXis-c2VmoiO7eb1rizFRItxne3Zh1FTITfVIhWWqvizF59.png) ![](https://remnote-user-data.s3.amazonaws.com/uhFqMCF5stzL9vCHgxGaFdG6b-op15tRGjPZjXOw6cs3md_GGVTRUmDV8emI1EGNhkHLx83bVtvrNkPTWMUYEtG483uDo8JseQb2N86Y3M22dzbihgJNRXrsIT1dBnth.png) 
        - Ordenaciones en una secuencia de instrucciones:
            1. Orden de Captación ⇒ orden en que aparecen las instrucciones en el programa y se codifican.
            2. Orden de ejecución ⇒ orden en el cual las instrucciones que se codifican pasan a ejecutarse en un determinado orden.
            - El orden en el que las instrucciones modifican los registros y la memoria modifican el estado interno de la máquina. El procesador superescalar debe ser capaz de identificar el paralelismo entre instrucciones que exista en el programa y organizar la captación, decodificación y ejecución de instrucciones en paralelo.
            - La única restricción es que el resultado del programa sea correcto.
        - Cauces Superescalares
            - Etapas:
            - 
    - 
    - 
    - 
- Formulario
    - Tema 1
        - Tiempo CPU
            - $CiclosPrograma * T_{ciclo}$ 
            - $CiclosPrograma \div Frecuencia_{CPU}$
            - $NI*CPI*T_{ciclo}$ 
                - NI⇒Numero de instrucciones
                - $NI=N_{oper} \div OP_{instr}$
                    - $N_{oper}$⇒Nº de operaciones que realiza el programa
                    - $OP_{instr}$⇒ Nº de operaciones por instrucción 
        - Cantidad de ciclos:
            - CP→Ciclos programa:
                - $\sum CPI_i * I_i$  
                    - $I_i$⇒ Cantidad de instrucciones del tipo i
                    - $CPI_i$⇒ Cantidad de ciclos que tarda en ejecutarse una instrucción del tipo i 
            - CPI→Ciclos por isntrucción.
                - $CPI=CP \div NI$ 
                - $CPI=CPE/IPE$
                    - CPE→Ciclos por emisión (Nº mínimo de ciclos transcurrido entre los instantes en el que el procesador puede emitir instrucciones)
                    - IPE→Instrucciones por emisión(cantidad de instrucciones que pueden emitirse a la vez cada vez que se realiza una emisión de instrucciones.
        - $T_{ciclo}=1\div Frec_{cpu}$  
        - Ganancia:
            - $$S_p=V_p\div V_1 = T_1 \div T_p$$ 
                - $V_p$  ⇒ Velocidad después de mejora
                - $V_1$ ⇒ Velocidad antes de mejora
                - $T_1$ ⇒ Tiempo antes de la mejora
                - $T_p$ ⇒ Tiempo después de la mejora
        - Productividad:
            - $$P(n)=n\div T_p(n)$$
        - Ley de amdahl
            - La ganancia del tiempo de ejecución en un código viene determinada por una cota superior:
            - $$s \leq p \div (1+f(p-1))$$
                - p ⇒ factor de mejora (si una instruccion se ejecuta en x del tiempo inicial, la mejora es $(x)^{-1}$
                - f ⇒ Fracción del tiempo de ejecución en el que no se aplica la mejora en el código.
    - Tema 2 
        - Ganancia en prestaciones:
            - $$S(p)=prestaciones(p) \div prestaciones(1) = T_s \div T(p)$$ 
            - $T_s$⇒ Tiempo ejecución en secuencial
            - $T(p)$⇒ Tiempo de ejecución con p procesadores en paralelo. 
        - Tiempo ejecución en paralelo:
            - $$T_p(p,n)=T_c(p,n)+T_0(p,n)$$
                - $T_c(p,n)$⇒ Tiempo que tarda en ejecutarse la parte en paralelo
                - $T_0(p,n)$⇒ Tiempo que tarda en ejecutarse la parte en secuencial 
    - Tema 3
    - Tema 4 
    - 
