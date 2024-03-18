- Clasificación del Paralelismo implícito en una aplicación
    - Tipos de paralelismo
        - [Paralelismo Implícito](../../../../Paralelismo Implícito.md) 
            - Criterios de clasificación del [Paralelismo Implícito](../../../../Paralelismo Implícito.md) 
                - Granularidad
                    - Definición→Tamaño de lo que se puede ejecutar en paralelo
                    - < Tamaño ⇒ Granularidad mas fina
                    - ![](https://remnote-user-data.s3.amazonaws.com/1QRqMSKiR9oIiR0Qz41XRM56BiKxcnP6sVBQ8pDwEUxi_c6XW4H2upRNhFljQDrzl05x-xrqzTRD_Kud218yNDpyq5459LmJRZq_Kn1ciis_i4oVS6VJK73xd91mvgat.png) 
                - Paralelismo de Tareas ([TLP](../../../../TLP.md)) 
                - Paralelismo de Datos ([DLP](../../../../DLP.md)) 
                - 
        - [Paralelismo Explicito](../../../../Paralelismo Explicito.md) 
            - Criterios de clasificacion del [Paralelismo Explicito](../../../../Paralelismo Explicito.md)
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
    - [Computación Paralela](../../../../Computación Paralela.md)
    - [Computación Distribuida](../../../../Computación Distribuida.md) 
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
                    - [Multicomputador](../../../../Multicomputador.md)
                    - [Multiprocesador](../../../../Multiprocesador.md) 
                - **Diferencias:**
                    - ![](https://remnote-user-data.s3.amazonaws.com/z0PMrM1bQjWfac1fl5P6pJzh5CrPNd3IstDUypmyan_2SWxRg8zt0R6SvoM3uomfajNsAK3YDFZbIdrQZndpZZvUxx7wS6JIhWmujzftHMHMARCu6eBsdmus8JqMzgZA.png) 
                    - ![](https://remnote-user-data.s3.amazonaws.com/f8W_QxDDF8reOrFQPbiTO-qVQPveN5I6WspduposFQcxU3S4jaVArPDgcCiazYy8wPX8vmPR0twk7uKxyeJgspd5cWifhzuca2ReGgLvmOc7edqofcmD_v9ksNM0JN2m.png) 
                        - NORMA↔Memoria distribuida físicamente, comunicación a través de mensajes.
                        - NUMA↔Memoria físicamente distribuida pero tratada en conjunto como una única memoria. Genera tiempos de acceso a memoria poco consistentes en función de la "cercanía" del dato a buscar.
                        - CC_NUMA↔Como un NUMA pero con protocolos Hw y Sw para la coherencia de caches
                        - COMA↔Cada memoria local actúa como una cache del procesador. La memoria interna del sistema es al suma de todas las caches de los procesadores.
- 
- 
