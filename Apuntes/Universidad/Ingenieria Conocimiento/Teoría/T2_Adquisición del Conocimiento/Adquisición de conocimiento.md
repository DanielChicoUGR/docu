- Introducción
    - Adquisición de conocimiento→Proceso de recolección de información de cualquier fuente existente necesaria para construir un Sistema Basado en Conocimiento. Esto se realiza por lo general en el desarrollo del problema
    - Objetivo Adquisición conocimiento→Proporcionar a cada etapa la información que se requiere en cada momento del desarrollo.
    - Este proceso se realiza en paralelo a todas las etapas de diseño de un SBC y forma parte de cada etrapa del desarrollo de este
    - Situación actual:
        1. La adquisición de conocimientos es la tarea más importante del desartrollo de un SBC.
        2. Se pueden aplicar algunas técnicas propias de IA pero como herramientas.
        3. No existe un método automatizado de Adquisición del Conocimiento.
        4. Existen unas metodologías utilizadas para adquirir correctamente el conocimiento.
    - En general
    - ![](https://remnote-user-data.s3.amazonaws.com/slatZ-pdn_E46rOGTUvC6WcgSQqfowRUex_cNt_0eekIjRDrYpluvTFo2Z5gJo5rFXsNie5psw-OOGGKCHkFvhItquGkWHdehtlrxp2Ba-IhplTCvhxQ50qSqSqpMEqw.png) 
- Fuentes de conocimiento:
    - Personas:
        - Segun como interactuen con el SBC se clasifican en↓ ↓ 
            - Expertos
            - Directivos
            - Usuarios
        - Expertos→Poseen la mator parte de los conocimientos
        - Directivos→Poseen los objetivos del proyecto, al alcance del sistema, el contexto donde será instalado.
        - Usuarios→Comprender el tipo de persona que interactuará con el sistema, Sus necesidades y requisitos.
    - Documentos
        - Segun su tipo se clasifican en ↓ 
            - Resultados de estudios e investigaciones: Datos, estudios, informes, resultados estadísticos...
            - Publicaciones especializadas. Contienen la información mas al dia (actualizada)
            - Material utilizado para la formación. Suele contener conocimiento expuestos de manera especialmente clara
            - Casos :Algunas empresas suelen registrar los casos que se les presentan en forma de órdenes de reparación, fichas de clientes o pacientes, estudios o almacenamiento de casos.
    - Experiencia
        - Consta de:
            1. Observación (visitas)→útil para clarificar ideas y entender el esquema general del proceso. Es mejor que explicitar el conocimiento.
            2. Documentos informales→Notas manuscritas, ayudas en el puesto de trabajo para los trabajadores en el dia a dia (conocimiento heurístico )
- Extracción y Educción:
    - Extracción de conocimiento→Cuando la fuente de conocimiento se presenta en forma escrita o registrada
    - Educción de conocimiento→Cuando los conocimientos se obtienen directamente de humanos. 
    - Proceso de adquisición del conocimiento. ↓ 
        1. Estudio del problema ⇒ Primeras reuniones y estudio de viabilidad(de expertos, directivos y usuarios).
        2. Extracción de conocimientos de la documentación
        3. Educción de conocimientos (del experto)
            1. Interrogatorio inicial
            2. Investigación profunda
- Estudio del problema
    - **Objetivos:**↓ ↓ 
        - Determinar los requisitos funcionales del sistema, o, en su caso, las necesidades de los usuarios del futuro sistema.
        - Definir el problema formalmente, se define como obtener unos valores de salida para unos valores de entrada por medio de una función.
        - Se debe introducir al Ingeniero de Conocimiento en el dominio a un nivel tal que sea capaz de desarrollar un estudio de viabilidad del Sistema Experto donde se determine si la tarea del experto es tratable o no, mediante la Ingeniería del Conocimiento.
    - Primeras reuniones
        - Se busca conocimiento generales, no de detalle, así como familiarizarse con la terminología del dominio. El ingeniero debe centrarse en el entorno de la tarea y los usuarios
        - Hay que dirigir la entrevista a definir el problema:
            1. Entradas
            2. Salidas
            3. Interacción con el sistema
        - Hay que conseguir el esquema general del proceso de razonamiento en formas de tareas, subtareas y las relaciones y dependencias entre ellas.
        - Analizar la viabilidad de obtener los hechos en que se basa el razonamiento.
        - Evitar a toda costa opiniones e ideas infundadas que interfieran con los resultados
        - Con una o dos reuniones deberia de bastar para zanjar estos asuntos
    - Analisis de Viabilidad
        - Se realiza después de las primeras entrevistas
        - Se deben responder ↓ 
            - Es factible obtener los datos de entrada?
            - Cuanto coste tendría?
            - El esquema general del proceso de razonamiento de puede representar?
            - Cada tarea podría representarse como un SBC simple mediante un modelo de representación del conocimiento básico?
        - Extracción del conocimietno
            - Objetivo→Aprender del domino tanto comp sea posible antes de comenzar las sesiones con el experto
            - Se pretende reducir/evitar el tiempo que en otro modo el experto usariaa en poner al tanto al ingeniero en el tema.
            - Consultas con el experto
                - Que debe traer ↓ 
                    - Documentos importantes a consultar
                    - MAterial relevante de los manuales 
                    - Listado de detalles que no aparecen en la documentación pero que es funsdamental para el desarrollo de la tarea.
                    - Señalar los puntos dnd la práctica real difiere de los procedimientos documentados .
                - Analisis extructural de textos
                    - Ante un determinado texto se establece una serie de terminos que deben ser buscados en el texto
                    - Terminos a buscar **preestablecidos** por la técnica y **dependientes** del dominio.
                    - Los terminos a buscar están preestablecidos pero son independientes del dominio
                        - **Ejemplo ⇒ **X se define como Y, X está relacionado con Y
                    - **Terminos independientes del dominio**
                        - Los terminos independientes del dominio son→Conceptos y relaciones
                        - Se deben buscar ↓ 
                            - Estructuras tipo Definicion ⇒ Conceptos y estructuras
                            - Estructuras tipo Afirmación Relacional ⇒ Relaciones
                        - Permite extraer conocimiento sin entender el tema por completo
                        - Para realizar el analisis se necesita ↓ 
                            - Estructuras a buscar y tipo de conocimiento que se obtendrá de cada una independientemente de que sea un concepto, característica, relación o valor.
                            - Un modo de detectar esas estructuras
                        - **Tipos de esxtructuras a buscar:**
                            - **Definiciones**→Introducción de un nuevo concepto en el texto
                            - **Afirmaciones**→Una frase que establece una verdad, se buscan aquellas afirmaciones que expresen relaciones entre conceptos
                            - **Leyes**→Establecen los principios básicos del dominio y y fijan el funcionamiento del mismo..
                            - **Procedimientos**→Establecen los pasos para la resolución de problemas en el dominio.
                                - Los conocimientos proporcionados por esta estructura están más allá del objetivo de la extracción de conocimientos a partir de la docu.
                        - **Modo de detectar estructuras:**
                            1. Busqueda de patrones ↓ 
                                1. Definiciones ⇒ A se usará para B, A es un B que C, A está compuesto de B y C...
                                2. Patrones ⇒ A es causa de B, A se relaciona con B, A es finalidad de B...
                            2. Buscar titulos de secciones, subsecciones y textos en negrita o cursiva
                            - El Trabajo es simple y tedioso
                                - Hay que leerse el texto deteniendose solo en las definiciones y en las afirmaciones de relación, estas frases se señalan
                                - Analizar las frases señaladas para extraer los Conocimientos buscados
                            - PAra erealizar esta tarea se usa software como Word2Vec
                - Educción de conmocimientos
                    - El ingeniero de conocimiento deberá marcar la perspectiva y profundidad deseada en cada sesión
                    - Dada la complejidad intrinseca del proceso, cada sesión deberá ser controlada en muchos otros aspectos.
                    - Ciclo de Educción
                        - Fases ↓ 
                            - **Preparación de la sesión**: Información a tratar, amplitud o profundidad de cada una, técnica adecuada y preparación de preguntas
                            - **Sesion:** Repaso del analisis de la última sesión, explicación al experto de los nuevos objetivos de la nueva sesión, educción y comentarios del experto
                            - **Transcripcción: **Se debe escribir la entrevista mas que grabarla
                            - **Analisis de la sesión** ↓ 
                                1. Lectura para obtener una visión general
                                2. Extraer conociminetos concretos: subdominio, problemas, conceptos, tareas, relaciones
                                3. Lectura para recuperar detalles olvidados
                                4. Crítica para mejorar por el ingeniero de conocimineto
                            - **Evaluación: **LAs preguntas que se debe resolver el IC son : Se ha conseguido los objetivos?, es necesario volver sobre el mismo objetivo? numero y tipo de sesiones necesarias para cubrir el area.
                        - Técnicas de educción:
                            - **Métodos directos**→Se le pregunta al experto directamente que es lo que sabe, el experto es la única fuente de información y el IC confia plenamente en lo que dice el experto. 
                                1. Entrevistas
                                2. Cuestonarios
                            - **Métodos indirectos**→Se utilizan porque no siempre los expertos pueden acceder a sus de tellaes de los conocimientos o procesos mentales y para confirmar lo adquirido con las tecnicas directas.
                            - **Técnicas** ↓ 
                                - Entrevistas (Abiertas o estructuradas)
                                - Cuestionarios
                                - Observación de tareas habituales
                                - Incidentes críticos 
                                - Clasificación de conceptos
                                - Analisis de protocolos
                                - Emparrillado
                                - Inducción
                    - Entrevista abierta
                        - El IC plantea de manera espontanea las preguntas al experto. Esto no quiere decir que esta técnica no requiera de planificación y control
                        - El IC habrá fijado el tema o perspectiva a tratar con el esperto asi como la profundidad de los conocimientos a educir
                        - Esta técnica es preferible usarla cuando el IC carece de un conocimiento minimo del tema fijado.
                    - Entrevista estructurada
                        - El Ic planifica de antemano las preguntas que debe realizar al experto durante la sesión
                        - Debe formular y agrupar las cuestiones lógicamente. Normalmente, estos conjuntos de cuestiones conciernen a acciones o procesos identificados en sesiones anteriores.
                        - El IC plantea una serie de cuestiones sobre un determinado objeto o atrivuto y una vez resueltas pasa al grupo siguiente.
                        - Las preguntas a plantear deben centrarse en los conocimientos del experto (Conceptos, relaciones e inferencia del experto)
                    - Limitaciones de las entrevistas
                        - **Puntos Fuertes** ↓ 
                            - Compilar los conceptos básicos de la tarea
                            - Obtener información conceptual implicada en el problema
                            - Extraer conocimientos de relaciones, valores y acciones
                        - **Puntos débiles** ↓ 
                            - Consume mucho tiempo, sobre todo para el IC
                            - Confia en la memoria del experto
                            - Existen problemas con el lenguaje
                        - **Problemas del lenguaje** ↓ 
                            - Eliminación de componentes clave en un proceso de razonamientos
                            - PAlabras con referencias no especificadas
                            - Referencias hechas con comparativas
                            - Condensación, de palabras, de procesos complejos
                            - Implicación de una conexión causal entre eventos ⇒ ??????? (No explicarse bien dando a entender otra cosa)
                - Observación de tareas habituales
                    - La mejor forma de ver como un experto hace un juicio es observarlo trabajar. 
                    - Registrar las acciones del experto tomando notas y siguiendo sus razonamientos en el hambito de trabajo, ya sea in situ o en diferido con una grabación
                    - El IC no debe intereferir en las tareas cotidianas del experto
                    - Se podríá entender como el entrenamiento a un novato en la profesión
                    - **Ventajas**
                        1. Proporciona al IC una primera idea de conocimientos y habilidades implicadas en el dominio
                        2. PRoporciona conocimientos básicos del dominio y ayuda al IC a comprender la tarea del experto
                        3. Es útil para captar conocimientos procedimientales o para entender características peculiares de los usuarios del SBC
                    - **Inconvenientes:**
                        1. Si las tareas habituales son poco informativas acerca el razonamiento del experto este méþodo sum8inistra poco conocimiento
                        2. Consume muxcho tiempo y puede llegar a ser inoportuno y fastidioso
                - Otras Técnicas
                    - **Tecnica de las 20 preguntas** 
                        - El IC se inventa un problema para que el experto lo resuelva, para ello el experto solo dispone de 20 preguntas al ingeniero. Sirve para conocer la info relevante que usa el experto
                        - Es una variante de la observación de tareas habituales
                    - **Incidente Críticos** 
                        - Consiste en que el experto describa casos particularmente interesante y comentar como lo resolvio, esta tecnica es interesante ya que hace que el experto comente detalles que en otro momento hubiera ignorado
                        - Una variante es exponer casos imaginarios y ver como el experto los resuelve
                    - **Imposición de restricciones** 
                        - PRetende que el experto verbalice ciertas deducciones que en un caso familiar pasaría por alto, imponiendo limitaciones en el uso de recursos
                        - Se puede restringir el tiempo dado para resolver el problema (Se necesita respuesta rápida) o la información disponible (faltan datos de entrada)
                        - Es util para educir cierto tipo de conocimiento como lo que pueden ser las prioridades de atención del experto
                    - **Clasificación de conceptos** 
                        - Se obtienen un conjunto de conceptos del tema a trata, que cubran ampliamente el dominio. Estos conceptos se transfieren a una ficha y se le pide al experto que los clasifique en una serie de grupos. Describiendo lo que cada grupo tiene en comun, luego se compara cada ficha pra formar una gerarquía.
                        - Esto funciona ya que hay cosas que el experto ya da por obvio, y esto sirve para obtener relaciones entre los conceptos mas obvios
                        - Esta técnica es especialmente aconsejable cuando hay un gran número de conceptos en un dominio, de modo que se requiere de una estructuración para que sean manejables
                    - **Cuestionarios**
                        - Consiste en realizar una entrevista estructurada al expertod e manera indirecta a traves de cuestionarios. 
                        - frente a las entrevistas, tiene la ventaja de que se puede acumular información eficientemente.
                        - Los cuestionarios pueden ser muy apropiados para describir los conceptos, revelar relaciones en el dominio y determinar incertidumbre.
