- Definición de modelo de datos 
    - Modelo de datos↔Mecanismo formal para representar y manipular información de manera general y sistemática. Consta de:
        1. Notación para describir datos.
        2. Notación para describir operaciones
        3. Notación para describir reglas de integridad. 
    - Modelado Lógico→Trasladar un esquema lógico de una BD en función de una estructura implementable
- El modelo de datos relacional. Estructura de datos. Integridad.
    - Estructura de datos relacional.
        - El modelo de datos relacional abarca 3 ámbitos distintos sobre los datos:
            1. La estructura para almacenarlos
            2. La integridad
            3. LA consulta y manipulación
        - Definiciones iniciales:
            - Atributo↔Cualquier elemento de la información subsceptible de tomar valores
            - Dominio↔Rango de valores donde toma sus datos un atributo. A priori se considera finito.
            - Relación↔Dados los atributos Ai (i=1,2...n) con los dominios Di (i=1,2...n), Definimos relacion asociada a A1,A2...An a cualquier subconjunto del producto Cartesiano D1xD2x...xDn
                - Propiedades  ↓ 
                    - No hay orden en las tuplas
                    - No hay orden en los atributos
                    - No hay tuplas duplicadas
                    - El esquema de toda relacion incluye una clave primaria
            - Tupla↔Cada una de las filas de una relación
            - Cardinalidad de una Relación R↔Numero de tuplas que contiene. Varia en el tiempo
            - Esquema de una relación R↔Atributos de la relación junto a su dominio.
            - Grado de una relación↔Numero de atributos de su esquema. Invariante en el tiempo
            - Instancia de una relación↔Conjunto de tuplas que componen la relación en cada momento.
            - Esquema de una base de datos relacional↔Colección de esquemas de relaciones junto con sus restricciones de integridad.
            - Instancia o estado de una base de datos↔Colección de instancias de relaciones que verifican las restricciones de integridad.
            - Base de datos relacional↔Instancia de una base de datos junto con su esquema.
            - Superclave↔Cualquier conjunto de atributos que identifican univoca mente a cada tupla de una relación.
            - Clave de una relación↔Conjunto mínimo de atributos que identifican univocamente a una tupla en una relación (Superclave minimal)
            - Clave Candidata↔Atributo o conjunto de atributos de una relacion que identifican a cada tupla en una relacion y que, ademas, no existe un conjunto menor de atributos que la identifiquen
        - **Una base de datos relacional es un conjunto finito de relaciones.**  
        - Propiedades de la estructura de datos relacional.
            - **Condición de normalización**→Todos los valores de los atributos de una relación son atómicos
                - Valor Atómico→Valor/Dato simple, no estructurado.
            - Cuando una relación cumple la condición se dice que se encuentra en Primera Forma Normal. 
            - **Consecuencias de la condición de normalización** ↓ 
                - No hay valores de tipo conjunto.
                - No hay valores de tipo registro.
                - No hay valores de tipo tabla.
            - **Clave Candidata (CC) y primaria (CP) (formal)**
                - $R[A1,A2,...,An], PK ⊆ {A1,A2,...An}$  Se denomina Clave Candidata ⇔ Se cumplen ↓ 
                    - Unicidad:  No existen dos tuplas de la misma relacion con la misma Clave primaria
                    - Minimalidad: No existe un subconjunto de la clave primaria que cumpla la condición de unicidad.
    - Restricciones o reglas de integridad
        - **Condiciones de integridad **→Normas que mantienen la corrección semántica de una base de datos.
        - Integridad de entidad:
            - Definición:→Un atributo que forma parte de la clave primaria de una Tupla en una relación no puede ser un valor nulo.
        - **Clave externa**  
            - Definición:→conjunto de atributos de una relación, que es una clave en otra relación.
            - Podemos ver una clave externa como un conjunto de atributos de una relación cuyos valores en las tuplas deben coincidir con valores de la clave primaria de las tuplas de otra relación.
        - Integridad Referencial: 
            - Definición:→Si una relación incluye una clave externa conectada a una clave primaria, el valor de la clave externa debe ser, bien igual a un valor ya existente en el dominio activo de la clave primaria, o bien completamente nulo.
            - Indica que las claves externas han de tener el valor de una clave ya introducida en la base de datos o un  valor nulo.
            - **Tareas del SGDB** ↓ 
                - Mantener unicidad de las claves primarias y de las claves candidatas.
                - Mantener la restricción de integridad e identidad frente a operaciones de inserción y actualización de datos.
                - Mantener la integridad referencial en: ↓ 
                    1. La inserccion
                    2. actualizacion 
                        - 
                    3. Borrado 
                        - Si se borra la clave primaria en al relacion referenciada ⇒ Borrado en cascada de todas las tuplas que referencian a esa clave primaria o poner valor nulo.
                    - 
- Otros modelos de datos.
    - Modelo Jerárquico:
        - Características: ↓ 
            - Nivel externo implementado con aplicaciones en cobol.
            - Carecia de lenguaje de consulta.
            - La estructura de datos basica era un arbol
                - Almacena Registro Maestro y Registros Secundarios
                - 
            - La BD es una coleccion de arboles
        - ![](https://remnote-user-data.s3.amazonaws.com/rxowwfOdnWZ-8CXrV27QpzuvjDfLMobxHXGO30Q-rGBsVEStWy_-Mg2j967s8NmaUSiY-4rH5tiNjimhkftep-MdflNjC3Aa9iuoLxyy7Ba66l2r33E2xLfnjXSvfLmC.png) 
        - **Ventajas:** ↓ 
            - Buena representación relaciones muchos a 1
            - Buena representación relaciones 1 a 1
        - **Inconvenientes:** ↓ 
            - Dificil de mantener la estructura en ficheros
            - DML dificil de implementar y usar
            - Redundancia necesaria para implementar relaciones muchos⇐⇒muchos muy costoso de mantener.
    - Modelo de Red:
        - **Caracteristicas :**
        1. Estructura de Datos ⇒ grafo
            - Nodo ⇒ Registro
            - Arista/Arco ⇒ Enlaces entre registros (punteros)
            - Relaciones entre conjuntos de entidades:
                - 
        - 
- 
- 
- 
- 
- 
- 
- 
