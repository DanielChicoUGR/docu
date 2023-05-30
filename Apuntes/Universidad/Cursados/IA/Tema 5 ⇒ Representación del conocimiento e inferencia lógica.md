- Representación del conocimiento en IA
    - Existen varias formas de modelar el mundo de un agente:
        1. Representaciones icónicas→Simulaciones del mundo que percibe el agente
        2. Representaciones descriptivas→Valores Binarios que describen aspectos ciertos o falsos sobre el mundo.
    - Las representaciones descriptivas tienen ciertas ventajas sobre las iconicas:
        - Son mas sencillas
        - Mas faciles de compartir entre agentes
        - Se pueden descomponer
    - Ademas, existe informacion del entorno del agente que no se puede representar mediante modelos icónicos, tales como:
        - **Leyes generales **(Todas las cajas azules pueden ser recogidas)
        - **Información negativa **(El bloque A no está en el suelo)
        - **Información incierta **(O bien el bloque A esta sobre el bloque C o sobre el bloque B)
        - Sin embargo, este tipo de información es fácil de formular como conjunto de restricciones sobre los valores binarios de las catacterísticas binarias del agente?
    - Conocimiento del mundo→Conjunto de restricciones que aplican sobre la realidad observable que conoce el agente.
    - A menudo, el conocimiento del mundo puede utilizarse para razonar sobre él y hallar nuevas características del mismo.
        1. **EJEMPLO:**  
            1. El conocimiento que se tiene es “Todos los pájaros vuelan”; y “Piolín es un pájaro”.
            2. Se puede razonar, por tanto, que “Piolín vuela”.
        2. **EJEMPLO:**
            1. Un robot sólo puede levantar un bloque si tiene suficiente batería y el bloque es elevable. Entonces, el conocimiento sobre el mundo es: “Si el bloque es elevable y hay suficiente batería, entonces es posible levantar el bloque”.
            2. El robot “sabrá” si es capaz de levantar el bloque a partir de este conocimiento sobre su entorno.
- El cálculo proposicional
    - Elementos de representación ↓ 
        - Proposiciones
        - Conectivas:
            - $$\land (y), \lor (or), \rightarrow (implica), \neg (negación)$$ 
    - Inferencia→deducciones con reglas, hechos y Modus-Ponens
    - **Ventajas:**
        - Representación de tipo general y decidible en un tiempo finito con la información disponible.
    - **Problemas:** 
        - Malo al intentar razonar sobre conjuntos de cosas
    - Reglas de inferencia:
        - Nos permiten producir nuevas [FBF](../../../FBF.md)s a partir de las que ya existen. 
        - Definición demostración:
            - Supongamos $\triangle$ un conjunto de [FBF](../../../FBF.md)s y una secuencia n de FBFs {$w_{1},w_{2},w_{3},...w_{n}$}
            - Esta secuencia de [FBF](../../../FBF.md)s se llama dedución o demostración de $w_{n}$ a partir de $\triangle$ ⇔ cada $w_{i} \in \triangle$ o $w_{i}$ puede inferirse a partir de [FBF](../../../FBF.md)s de $\triangle$.
            - Si existe tal demostración ⇒ decimos que $w_{n}$ es un **teorema **de $\triangle$, y decimos que $w_{n}$ puede demostrarse desde $\triangle$ con la siguiente notación :
                - $$\triangle \vdash w_{n}$$ 
                - $$\triangle \vdash_{R} w_{n}$$
$w_{n}$ se demuestra deste $\triangle$ mediante las reglas de inferencia $R$ 
            - 
    - Interpretación:
        - A la hora de resolver problemas con IA, el papel de la semántica es esencial: Hay que hacer una correcta **interpretación **del sistema lógico subyacente.
        - Conlleva asociar elementos del lenguaje lógico con su significado en el entorno del agente.
        - **Ejemplo:**
            - Se desea implantar el conocimiento: "Si la batería funciona y el bloque A está en el suelo, entonces se puede levantar"
            - **Definición de Atomos:** (Variables booleanas) 
                1. BATERÍA_OK
                2. ESTA_A_SUELO
                3. LEVANTAR_A 
            - **Definición **[FBF](../../../FBF.md):
                - $$BATERÍA-OK \land ESTA-A-SUELO \supset LEVATAR-A$$ 
            - En un agente cuyo objetivo sea "Levantar el bloque A", con este conocimiento puede especificar acciones que debe llevar a cabo para realizar su acción 
    - Tablas de Verdad:
        - Establecen la semántica de las conectivas proposicionales
        - Para una representación interna de un agente con n características, el numero de combinaciones (formas de ver el mundo) es $2^n$ 
        - ![](https://remnote-user-data.s3.amazonaws.com/MfSDBI-OSsY0nkGOhIh4kWlvH_5pwgHwpyjs0GnZ4Jo3Jz_wo7h40HSWhxi276XFt39Bxq4mDKbHApxTMA_fNPH9DpLEqytoon_bFwkySOiPAEEpIH-rk_b0s8LeOr4R.png) 
    - Satisfactibilidad y modelos:
        - Una **interpretación satisface una **[FBF](../../../FBF.md) ** **cuando al [FBF](../../../FBF.md)se le asocia el valor V(verdadero) bajo esa interpretación.
        - **Modelo**→Interpretación que satisface una [FBF](../../../FBF.md)  
        - Bajo una interpretación una FBF debe indicar una restricción que nos informe sobre algún aspecto del mundo.
    - Validez y equivalencia:
        - [FBF](../../../FBF.md) Válida→Ocurre cuando la [FBF](../../../FBF.md) es cierta dando igual la interpretación que se le asocie.
            - Las interpretaciones válidas no aportan conocimiento util y deben ser evitadas
        - [FBF](../../../FBF.md)**s equivalentes **→** **Dos o mas FBFs son equivalentes ⇔ sus tablas de verdad son identicas
            - En el diseño de agentes se deben evitar FBFs con interpretaciones equivalentes para hacer mas eficiente el proceso de razonamiento.
    - Consecuencia lógica: 
        - Si una [FBF](../../../FBF.md) w tiene valor verdadero bajo todas aqueyas interpretaciones para las cuales cada una de las [FBF](../../../FBF.md)s del conjunto $\triangle$ tienen valor verdadero, decimos que $\triangle$ lleva lógicamente a w
        - La noción de consecuencia lógica nos proporciona cierto mecanismos para demostrar que si ciertas proposiciones son ciertas entonces otras deben serlo también.
        - $$\triangle \vDash_R w$$ 
    - Solidez y completitud:
        - Solidez→Un conjunto de [FBF](../../../FBF.md)s $\triangle$ es solido ⇔ $\exists w$ |  $\triangle \vdash_{R} w_{n}$  y $\triangle \vDash w$  
        - Completo→Si para el conjunto de [FBF](../../../FBF.md)s $\triangle$ y para la [FBF](../../../FBF.md) w, tenemos que siempre que  $\triangle \vDash w$, existe una demostración de w a partir de $\triangle$ utilizando el conjunto de reglas de inferencia R, decimos que R es completo. 
- Cálculo de predicados
    - El cálculo proposicional impone una serie de limitaciones debido a su construcción. Que acaban implicando en tener que tener un literal por cada posible estado a tener en cuenta. Este problema lo solucionó el lenguaje natural hace tiempo al hacer uso de la definición de objetos y de las relaciones entre ellos.
    - El cálculo de predicados usa esta configuración, absorviendo al calculo proposicional para que se exprese como un caso particular del calculo de predicados.
    - Elementos de representación
        - Terminos ↓ 
            - Constantes (UGR)
            - Variables (X toman valores de distintas constantes)
            - Funciones (siguiente(x))
        - Formulas atómicas→Predicados formados sobre Terminos
            - Trabaja_como(empleado1,director) ⇒ (True - empleado1 es director // False - empleado1 no es director)
            - tiene_hijos(empleado1,1) ⇒ (True -empleado1 tiene 1 hijo // False ⇒ empleado1 no tiene un hijo)
        - [FBF](../../../FBF.md)→Fórmulas atómicas unidas por conectivas ($\land, \lor, \rightarrow , \neg$) y cuantificadores ($\exist$, $\forall$)  
            - ∀ X,Y trabaja-como(X,director), tiene-hijos(X,Y), Y<=2→gana (X,60000) ⇒ Toda Persona que trabaja como director, Si tiene al menos 2 hijos entonces cobra 60k
    - Reglas de Inferencia 
        1. Todas las de lógica proposicional
        2. Instanciación universal→a partir de una verdad sobre cada miembro de una clase de individuos da la verdad sobre un individuo en particular de esa clase
$\forall X p(x) \rightarrow$ Se deduce p(a),p(b)...
            - ![](https://remnote-user-data.s3.amazonaws.com/ClG8YbzB8QTBPXBE2aCJ-MQUC_EEKY-IEz3lettTcQ4fpQIh_zNT-0lb_050qj3LZHNqKXba0UzEclDZ5lZX5H9jyaqKTJEbAcfA4DbHmDlaV6E1_I28w5cGq2pLwDIo.png) 
    - Características del cálculo de predicados:
        - Ventajas:
            - Es un sistema Solido
            - Es un sistema Completo
        - Desventajas:
            - Es un sistema semidecidible. 
            - El problema de la refutacion se presenta de tipo NP-Duro si se da el caso
- Introducción a los sistemas basados en el conocimiento. 
    - Una gran cantidad de aplicaciones realies de la IA se basan en la ecistencia de una gran masa de conociemiento:
        - Diagnostico médico
        - Diseño de equipos
        - Sistemas de recomendación
        - etc
    - Este tipo de sistemas se denominan **Sistemas Basados en el Conocimiento**, ya que este ocupa la parte central de la solución al problema a resolver.
    - Sistemas de conocimiento(SBC):
        1. Base de conocimiento (BC):
            - Almacena el conocimiento experto necesario sobre el problema a resolver. Puede ser
                - Estática ⇒ su tamaño no varía con el tiempo
                - Dinámica ⇒ Se puede añadir nuevo conocimiento si es necesario
        2. Motor de Inferencia
            - Permite razonar sobre el conocimiento del la BC y los datos proporcionados por un usuario
        3. Interfaz de Ususario 
            - Para la entrada y salida de datos.
    - Sistemas Expertos basados en Reglas (SEBR):
        - Es una modificación de un SBC en el cual el conocimiento se almacena en forma de hechos.
        - Estas reglas y hechos se implementan a traves del calculo de predicados
        1. Proceso de construcción:
            1. Se extrae el conocimiento experto
            2. Se modela y se adquiere conocimiento, utilizando un lenguaje adecuado
            3. Se crea la BC con el conocimiento adquirido
        2. Interfaz de Usuario:
            - Para la entrada y salida de datos.
        3. Subsistema de explicación:
            - Para los casos en los que sea necesario indicar al usuario porqué se llega a esas conclusiones que se llegan
        4. Motor de inferencia:
            - Para razonar sobre la Base de Conocimiento y los datos proporcionados por el usuario
        5. Esquema general de diseño
            - ![](https://remnote-user-data.s3.amazonaws.com/AAeRSn8FBIulrloF4yTFHpij4hfFPpZEm8cNt5QflGQvr5U5XycNODDsk-Mm1gxqjhNqbRPJS2n_9aKuL-kJtiRSg_wqM4PekVmBHtQ_pnjRTZkpiDSQO8i3MNfxOoV9.png) 
**Memoria de Trabajo **→ contiene la información relevante que el Motor de Inferencia está usando para razonar las respuestas para el usuario.
    - Otros modelos de representación del conocimiento:
        - Organización jerarquica:
            - ![](https://remnote-user-data.s3.amazonaws.com/o21GOVsDtgnlna5SU8U2SUsvSRQuLCaoO_w8q5LT6GD4Mbj0zg02uqNtF9_XuIM22rt2WF6QE8Q7kNzBmMyikYgC5LBbLbfoRyRLM43uXdPRVYqRAimogyjsgwbmkrNj.png) 
- 
