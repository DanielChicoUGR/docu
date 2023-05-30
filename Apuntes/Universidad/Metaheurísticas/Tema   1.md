- Resolución de problemas mediante algoritmos de búsqueda
    - Definiciones:
        - Objetivo Metaheurísticas→Resolución de problemas mediante procesos de cómputo
        - Solución→Sistema informático que implementa un algoritmo
        - Algoritmo→"Solucion" pero mas abstracto en el contexto de esta asignatura (La solucion a los problemas que se plantean son algoritmos en su definicion mas matemática)
        - Computabilidad→Capacidad de un problema para ser representado como un modelo de computo, mientras mas eficiente este modelo, mas computable es un modelo 
        - Complejidad
        - Exactitud→Capacidad de un algoritmo de devolver soluciones cercanas al optimo local 
        - Existen problemas reales (de optimización o búsqueda) de difícil solución que requieren de tareas tales como: Encontrar↓ ↓ 
            - El camino mas corto entre varios puntos
            - Un plan de mínimo coste para repartir mercancías a clientes
            - Una asignación óptima de trabajadores a tareas a realizar
            - Una secuencia óptima de procesos de trabajos en una cadena de producción
            - Una distribución de tripulaciones de aviones con mínimo coste
            - El mejor enrutamiento de un paquete de datos en Internet
        - Características de los problemas que resuelven estas técnicas ↓ 
            - Gran complejidad computacional (Problemas de tipo NP-Duros)
            - los algoritmos exactos (programación dinámica, Backtracking, B&B,...) son ineficientes o simplemente no se pueden aplicar
            - Se encuentran  en múltiples áreas de aplicación
            - En la práctica se resuelven mediante algoritmos aproximados que proporcionan buenas soluciones (no necesariamente la óptima) al problema en un tiempo razonable
    - Elementos de un algoritmo de Búsqueda
        - **Función objetivo**→una función con variables de restricción. Rstricciones del tipo $x =\  <\ >\ \leq \ \ge \beta$
        - **Espacio de Búsqueda**→Valores de las variables de decisión que serán evaluados durante el proceso de optimización.  Puede ser discreto/continuo contable/incontable
    - Representación del espacio de Busqueda:
        - ![](https://remnote-user-data.s3.amazonaws.com/M9ngQ0yt7yP0-VGmwHLBifOX2rkOn4hfXFJLPZkuVBJBKuqXyZy49ZRuP8-YAaxgNRV301p_uzO6rmJVgSSSKzRWKSYciUqwmAaNDeFRbP2Rd8Gt_NhBaLiHty7kHq8p.png) 
- Algoritmos aproximados
    - Los algoritmos aproximados aportan soluciones cercanas a la óptima en problemas complejos (NP-duros) en un tiempo razonable
    - **Cuando es interesante usarlos** ↓ 
        - Cuando no hay un método exacto de resolución, o este requiere mucho tiempo de cálculo y memoria.
        - Cuando no se necesita la solución óptima, basta con una de buena calidad en un tiempo aceptable.
    - Algoritmos de búsqueda.
        - Es un término utilizado para construir/mejorar soluciones y obtener el óptimo o soluciones casi óptimas.
        - Busqueda por entornos:
            - ![](https://remnote-user-data.s3.amazonaws.com/MPVnTXk63Ukt-jFlKy2pB73Rs8UER8F5V9ws856NZMkUUftQg_Bl4tD4jT-RyxnfVfJ5yTOqwXy6U-EgiSV03MYWANC02_qeclTgvvxX40wPJMSV08DuMMjC_zsEirqt.png) 
            - **Solución**→Representación de la solución del problema
            - **Entorno**→Soluciones cercanas en el espacio de soluciones
            - **Movimiento**→Transformación de la solución actual en otro (normalmente una solución vecina)
            - **Evaluación**→Se evalúa la factibilidad  de la solución y la función objetivo 
        - ![](https://remnote-user-data.s3.amazonaws.com/TFgqfsozaZuCpr1I0195w4ZOhd_xNAX0IbsHhWWhYu7o83K2Hoov5Xcg3eD5GuyefSKbzEgAqwdkYTj452QdCUUdWRLOouDUVBN5TR9I0oxBXMyffNVxZeLKE0yatRwi.png) 
- Metaheurísticas: Definición y clasificación
    - **Definición de Metaheurística**→Son una familia de algoritmos aproximados de propósito general. Suelen ser procedimientos iterativos que guían una heurística subordinada de búsqueda, combinando de forma inteligente distintos conceptos para explorar y explotar adecuadamente el espacio de búsqueda
    - Ventajas:
        1. Algoritmos de propósito general
        2. Gran éxito en la practica.
        3. Fácilmente implementables
        4. Fácilmente paralelizables
    - Inconvenientes
        1. Son algoritmo aproximados, no exactos
        2. Son no determinísticos (probabilísticos)
        3. No siempre existe una base teórica establecida.
    - Clasificación:
        1. Basadas en métodos constructivos
            - (mecanismos paraconstruir soluciones) GRASP, Optimización Basada en Colonias de Hormigas
        2. Basadas en trayectorias
            - (la heurística subordinada es un algoritmo de búsqueda local que sigue una trayectoria en el espacio de búsqueda): Búsqueda Local, Enfriamiento Simulado, Búsqueda Tabú, BL Iterativa, ...
        3. Basadas en poblaciones
            - (el proceso considera múltiples puntos de búsqueda en el espacio): Algoritmos Genéticos, Algoritmos Meméticos, Diferential Evolution, ...
- Metaheurísticas: Paralelización
    - Objetivos ↓ 
        - Preservar la calidad de las soluciones
        - Incrementa la calidad de las soluciones sin aumentar el tiempo de cálculo
        - Obtener soluciones de mayor calidad debido al efecto sinérgico de la distribución espacial de la búsqueda.
- Resumen:
    - Pasos a seguir en la resolución de un problema de optimización ↓ 
        1. Modelar el problema (Inspirandonos en modelos similares)
        2. Identificar si debería resolverse con metaheurísticas
            1. Complejidad y dificultad del problema
            2. Requerimientos
            3. Realizar una revisión del estado del arte en algoritmos de aptimización para resolver el problema
        3. Si se va a diseñar una metaheuristica, se debe determinar:
            1. Representación de las soluciones del problema, consistente con respecto a la función de evaluación y operadores
            2. Función objetivo, que guie la búsqueda hacia soluciones "buenas"
            3. Manejo de restricciones sobre el espacio de soluciones y los valores de las variables
        4. Elegir un entorno software para la implementación
        5. Toda metaheurística tiene parámetros que se deben ajustar para cada problema y que tienen influencia en la eficiencia y eficacia de la búsqueda
            1. **No existe un conjunto universal de parámetros**
        6. Evaluación del rendimiento de la metaheurística.
- 
