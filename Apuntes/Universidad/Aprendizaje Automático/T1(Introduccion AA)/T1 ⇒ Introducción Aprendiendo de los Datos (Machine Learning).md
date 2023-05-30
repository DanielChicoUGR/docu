- Paradigma
    - Un problema de ML se atraviesa dos etapas ?
      ?Aprendizaje ⇔Entrenamiento (Se debería de poder aprender cuanto se pueda {de los datos}/{del material} disponible)
      ? Verificación/Test (Debe responder de manera satisfactoria a nuevos datos del dominio
    - EL objetivo principal (y mas dificil de alcanzar) es aprender las reglas/funciones/conceptos validos para responder a cualquier tipo de pregunta del tema a tratar, no solo aquellos que se han entrenado previamente
    - Enfoques:
        - Aprendizaje autonomo ↓ 
            - Se centra en algoritmos precisos y eficientes para problemas a gran escala (El objetivo es la generalización fuera de la muestra)
            - Depende de los avances de las técnicas de optimización y regularización
            - Gran contra ⇒ Un **mal modelo** siempre es una posibilidad
        - Aprendizaje estadistico:
            - El objetivo prinicpal es la inferencia (explicar los datos) utilizando distribuciones de probabilidades específicas.
            - Buenos resultados solo bajo la hipotesis asumida
            - Muy poca atención a los problemas de gran escala 
        - Aprendizaje Bayesiano:
            - Un enfoque probabilístico completo que incorpora el conocimiento previo
            - Complejidad matemática y computacional
            - Muy poca atención a los algoritmos y a las cuestiones computacionales
            - Los modelos son buenos cuando las hipótesis se ajustan a los datos
    - ![](https://remnote-user-data.s3.amazonaws.com/Vv-Kx666ozIETvhOaL5IPfocmShSHVDtTsc5Ea05iHFZN_dpz3REk_JVP-A5_WLiAVAr9fLXtzGi3zn-NX6ARAAWZ9svgi0SNmztzOW--fWVVinM25DtNgofhj4eCHDc.png) 
El ordenador aprende un cálculo para resolver una tarea. Adecuado para el ordenador pero difícil para el ser humano.
    - Aprendizaje vs Diseño
        - Algunos enfoques solo utilizan datos para fijar algunos parámetros de un problema bien especificado ⇒ **Diseño** 
        - **Ejemplo**: Supongamos queremos construir un modelo para reconocer monedas a
partir de su tamaño y masa: {$(tamaño_i,masa_i), i=1,..,N$} 
        - Diseño ⇒ (Def informal) Recopilamos información sobre el tamaño y la masa de cada tipo de moneda y el número de monedas en uso. Construimos un modelo físico para la masa y el tamaño, teniendo en cuenta las variaciones por el uso y los errores medidos. Por último, construimos una destribución de probabilidad sobre (Tamaño,Masa) que queremos clasificar
        - Aprendizaje ⇒ (Def Informal) Recogemos datos etiquetados de cada tipo de moneda. El algoritmo de apredizaje busca una hipótesis que clasifique bien los datos. Utilizamos la hipótesis aprendida para clasificar nuevas monedas.
        - La información disponible sobre el problema es la clave para adoptar un enfoque u otro 
    - Aprendizaje Automático
        - Definiciones de aprendizaje:
            - Def1 (Arthur Samuel)⇒ El campo de estudio que da a losordenadores la capacidad de aprender sin estar explcítiamente programados.
            - Def2 (Tom Mitchell)→Se dice que un preograma informático aprende de la experiencia E con respecto a algunaclase de tareas T medido en rendimiento P, si su rendimiento al realizar tareas de T medido en P, mejora con la experiencia E
        - En general cualquier problema de aprendizaje autonomo puede asignarse a una de estas dos clases:
            1. **Aprendizaje Supervisado**::Aprender una función para **predecir etiquetas ** a partir de datos etiquetados de muestra
            2. **Aprendizaje no Supervisado**::Aprende propiedades de datos no etiquetados transformando las características observadas. 
    - Resumen:
        - Aprendizaje Supervisado ⇒ Datos de muestra + etiqueta
            - Aprendizaje Semisupervisado
            - Aprendizaje Activo
            - Aprendizaje en Linea?
        - Aprendizaje No supervisado ⇒ El sistema solo recive datos e intenta extraer patrones de ellos.
            - Aprendizaje Autosupervisado ⇒ Transforma los datos brutos en característixas destacadas resolviendo tareas previas que explotan las dependencias de los datos.
        - Transferencia de conocimientos ⇒ Como compartir concomiento entre diferentes tareas
        - Aprendizaje por refuerzo ⇒ El ajente interactua con el entorno. Aprende una dinámica local no una función global
- Aprendizaje Supervisado
    - Esquema de aprendizaje
        - ![](https://remnote-user-data.s3.amazonaws.com/ZlQSccVXoMIx-WepAJ2ILrp4tJwSSPmn9FuGqr6HRvQcSSK9MDxj9A8eKlq1V9k-JGonBMn6KL_B6kQ2EIwUFGAT278ZdbehzaEHiJ1BNIYI9ha8fs4gH4W4dJ8V7XHv.png) 
        - Suposiciones:
            1. La  única información disponible es la nuestra
            2. La función se calcula a partir de la muestra utilizando un criterio de aprendizaje
            3. La función calcula una predicción
        - **Tarea principal ⇒ **Como elegir una muestra y un programa de aprendizaje automático para encontrar una función de predicción precisa sobre toda la población
    - Extracción de características y representación de datos
        - A la hora de intentar dar una explicación formal de muchos eventos, actividades, objetos, seres... en las distintas maneras que se representan, nos encontramos ante un problema del cual no existe conocimiento formal como tal. El objetivo es estudiar los datos para intentar encontrar patrones que desconocemos a priori.
            - Patrones ⇒ Codificación/Representación
        - Aplicaciones:
            - reconocimiento del habla
            - Reconocimiento de caras
            - Traducción y redacción de documentos
            - Sistemas de recomendación
            - Pedicciones Bursatiles
            - Pronóstico y diagnóstico automáticos en medicina
            - ETC
        - Tareas del aprendizaje Supervisado
            1. Predicciones
            2. Regresión→El output es un numero real (vasriable continua) 
                1. Predecir la altura de una persona a partir de una muestra de datos
                2. Predecir la temperatura del día siguiente a partir de un registro anterior de temperaturas
            3. Clasificación→La salida es una atiqueta de clase (variable discreta o categoría)
                1. Predecir el tiempo de mañana (soleado,nublado...)
                2. Predecir si una imagen contiene un rostro
                3. Predecir si un email es spam o no
            4. Clasificación probabilistica→La salida es un vector de probabilidades sobre las etiquetas
                1. Predecir valores reales
                2. Resolver los mismos problemas que la clasificación
- Aprendizaje no Supervisado
    - Objetivo→Transformar los datos de la muestra a un espacio de representación mejor introduciendo una nueva medida de distancia entre las muestras ?
    - Enfoques clásicos ↓ 
        - Estructura Geométrica ⇒Agrupación
        - Dependencias que descubren patrones
        - Reducción de la dimensionalidad (Descartar variables inutiles)
- Autovigilado (self-supervised)
    - **Objetivo**→Resolver una tarea supervisada para desentrañar los datos muestreados en características más independientes que faciliten el procesamiento posterior. 
    - La tarea supervisada denominada tarea-pretexto se establece fácilmente a partir de los propios datos. Por ahora se centra principalmente en tareas de visión, habla y lenguaje natural.
- In a Nutshell
    - Supervisado:
        1. Transformación de los datos de entrada $T: D \rightarrow R$
        2. Minimizar un mapeo del error $f:D\rightarrow R \rightarrow L$ (Etiquetas GT)
    - Sin supervision
        - Transformación de datos de entrada $T: D \rightarrow R$
            - Descubrir nuevas distancias entre muestras
    - Autosupervisado
        - Transformación de datos de entrada $T: D \rightarrow R$ 
        - Minimizar un mapeo del error $f:D\rightarrow R \rightarrow L$ (Etiquetas GT)
        - Etiquetas sencillas no relacionadas con ninguna tarea específica
    - Terminologia
        1. D- dominio de los datos
        2. T - transformación de los datos observados
        3. f: la función de T a L ( lables), 
        4. GT: Ground-Thruth (terreno-verdad)
    - Diagrama de la configuración inicial de aprendizaje
        - ![](https://remnote-user-data.s3.amazonaws.com/KWy_alhzpminRsVRXG-Q_0Xu5z-NEwAQ6d3NCUVLf8EKeXjUjcuomFwcxvGJAbuPzuFcOHtBQqBusWVCRtofi9CG5Gg02Xiuz0Uq_rNs08W0ff0XZrS9umOCvSKdVJIu.png) 
- 
- 
